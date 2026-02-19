# Master thesis planning

### Title: Higher order unification with scope graphs

### First stage review: 24 February 2026

## Before first stage review
- Read up on Statix and previous work with dependent types in Statix.
- Understand how scope graphs can be leveraged for name binding (Scopes as types).
- Research higher order unification: how it differes from first order and under which conditions is it decidable.
- Learn about LambdaProlog and it's implementations (ELPI, ) which uses higher order pattern unification and backtracking. 

## After first stage review
- Investigate if we can use scope graphs in a similar way that lambdas are used in Higher order pattern unification. Providing solutions for metavariables requires the ability to bind names, which traditionally is done via lambda terms or metavariable closures. We should be able to use scope graphs for the same purpose.
- Devise the formal rules for typechecking and unification for a dependent type language that uses scope graphs.
- Implement a bidirectional typechecker in ELPI for a dependent type language with implicit arguments.
- Establish if higher order pattern unification can be done in Statix surface language or we need to modify Statix.
