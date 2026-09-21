# How to represent free and bound variables in Statix

The main challenge we have identified so far with Statix is encoding how we go under binders and how to perform capture avoiding substitution.


After consulting the literature for ways to encode the syntax of free / bound variables there are 3 solutions that are achievable in statix:
1. **DeBruijn indices.** will make substitution very easy, but not clear if I can still implement .ref and .type annotations for IDE services
2. **Locally nameless.** probably impractical in Statix since it is not clear how to generate fresh names.
3. **Scoped names.** This is the solution that Johan used. Wherever we encounter a binder $x$, we will replace it with ScopedName($x$, s) in the rest of the term. This should uniquely identify the binder and also make a difference between identifiers we parse from the user input and semantic ones that we generate. This approach will require big changes in the implementaiton of `check` / `infer`, as these functions can refine their input term and so must return a result. Currently `check` function has the signature: 
```
check : scope * meta_scope * Expr * Expr.
``` 
and will need to change to 
```
check : scope * meta_scope * Expr * Expr -> Expr
```

after checking the term `Lam("x", Var("x"))` we would return `Lam(Scoped("x", s), Var(Scoped("x", s)))`
Doing it like this might be very inneficient since for every binder you traverse the whole term, but at least substitution will be very simple.


#
> We found that generating fresh names is difficult in statix. A workaround that works is that you can create a fresh scope and use it's refference to uniquely identify an object: 
>```
>new s, Fresh(name, s)
>```

f :: (p : func) -> B p
f (\x -> \y -> _)

f (\x' -> \y' -> _ x' y')
p subst 
