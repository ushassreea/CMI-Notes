---
tags:
  - Note
aliases:
  - FPT
---
202403050803

Tags : [[Complexity Theory]]
# Fixed Parameter Tractibility
---
>[!info] Problems that are actually tractible.
>NP-Complete is a class that is defined as the hardest set of problems in NP, and SAT, being an NP-Complete problem should be hard to compute. Yes, in general, the best SAT-Solvers can take upto exponential time to solve a problem, but usually they are amazingly fast. Or that Model checking in LTL is PSPACE-Complete, but is Linear time for a given formula. FPT class gives one way to find such collections of problems.

Sometimes, having the general performance guarantees about a problem aren't specific enough. Usually the query is much smaller than a data-base, or the number of unique propositions in SAT formula is significantly less than the size of the formula. In those cases, the input is split into 2 parts, where the restriction is to have computation dependent of a subset of parameters an inputs in an efficient manner, i.e the way some parameters affect the computation time might not be relevent. This idea is captured by the FPT class.

>[!definition] Fixed Parameter Tractibility
>This is a class of decision problems where the input has 2 components, *the parameter* and *value*. Here we assume that the parameter does not make that much of a different to computation times so we say:
>
>A problem $M$ is in FPT class if there is an algorithm solving the problem in time 
>$$
>f(k)\cdot p(n)
>$$
>where $f$ is any computable function and $p$ is a polynomial (which can be different for each $k$).
>^a19740


>[!example]
>- Model Checking for LTL takes time $2^{O(k)}\cdot n$ 
>- A boolean formula of size $n$ with $k$ variables can be checked in time $2^k\cdot n$


---
# References
