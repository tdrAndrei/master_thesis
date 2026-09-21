# Master thesis planning

### Title: Higher order unification with scope graphs

### First stage review: 24 February 2026

## Before first stage review
- Read up on Statix and previous work with dependent types in Statix.
- Understand how scope graphs can be leveraged for name binding (Scopes as types).
- Research higher order unification: how it differs from first order and under which conditions is it decidable.
- Learn about LambdaProlog and it's implementations (ELPI, ) which uses higher order pattern unification and backtracking. 

## After first stage review
- Investigate if we can use scope graphs in a similar way that lambdas are used in Higher order pattern unification. Providing solutions for metavariables requires the ability to bind names, which traditionally is done via lambda terms or metavariable closures. We should be able to use scope graphs for the same purpose.
- Devise the formal rules for typechecking and unification for a dependent type language that uses scope graphs.
- Implement a bidirectional typechecker in ELPI for a dependent type language with implicit arguments.
- Establish if higher order pattern unification can be done in Statix surface language or we need to modify Statix.


1. Introduction
2. Background
3. Higher order unification theory
4. A Language with Dependent Types in Statix
    4.1. Pi types
    4.2. Variables and substitution
    4.3. Equality
    4.4. Statements and forward references
    4.5. Modules
5. Inference and unification
    5.1. Typed and untyped holes
        5.1.1. Tracking binders (context)
    5.2. Scope of metavariables
6. Comparing scope graphs and HOAS
    6.2. 
    6.1. Error messages
7. Related work
8. Conclusion
    8.1. Future work
        8.1.1. Primitives for Statix HOU (Signal that an _ depends on some terms from the object language)
        8.1.2. More dynamic algorithms for unification with constraint postponing
