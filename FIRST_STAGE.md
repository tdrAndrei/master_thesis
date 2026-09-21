# Notes
- What are the issues of doing higher order unification with scope graphs (in terms of name resolution)
MAIN ISSUE: typechecking dependent types requires beta reduction or at least weak head normal form. 
Typechecker will eventually try to reduce a metavariable and needs to know if it has an instantiation or not. 
If we leave the unification to statix, reducing a metavariable produces an unknown term. This behavior is not desired. If the meta has no instantiation, then it might lead to other unification problems which will narrow the solution. If it has an instantiation we want to substitute.

- Focus on making the typing rules first before actually implementing in Statix.
- Describe HOAS without focusing too much on lambda-prolog.
- Write about dependent type systems in the introduction.
- Add motivation about language workbenches. Why they are useful, how used are they currently and who uses them.
- Needs to be done 3+2 weeks after greenlight.

- Types are modelled as references to scopes. Since terms == types in dependent type languages, it makes sense for terms to contain references to scopes.