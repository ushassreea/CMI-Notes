---
tags:
  - Note
  - Incomplete
---
202404030904

Tags : [[Infinite State Verification]]
# Forward Reachability Tree
---
- Get a starting configuration
	- Keep firing transitions to get to new transitions and build a tree
	- cut it off the moment you see a configuration $X$ which is dominating a previously reached position $Y$
		- You have a wqo on states so that will happen, each run is finite.
		- the tree has bounded width
		- konigs lemma ftw
- FRT can be constructed in a finite (very large) amount of time (effectively)
- Transitive WSTS
	- If X -> X' then (Y>=X) ->* (Y' >= X')
- Strict WSTS
	- same as above but strictly
- Which makes termination problem decidable for Petri nets and LCS
- 

Exercise: vector addition system with states, how do we solve repeated coverability?
NOT THE KARP MILLER TREE



---
# References
