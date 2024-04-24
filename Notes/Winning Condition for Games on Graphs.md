---
tags:
  - Note
  - Incomplete
---

202403061703

Tags : [[Games on Graphs]]
# Winning Condition for Games on Graphs
---
The winning condition is a set of runs $\mathcal W$, where w run is an infinitely sequence of states. If the players play a game such that $\sigma$ is the run. We say Rajnikant wins is $\sigma\in \mathcal W$ otherwise Sreevani wins.

These games are $0$ sum, so exactly one the two players always wins.

>[!attention] Finite Runs
>There is one situation where the game can end after a finite number of steps.
>If the token ends up in a state with no out-neighbours. Then the game is terminated.
>In such a case, the winner is whichever player the set is associated with.

Some of the standard *Winning Conditions* for games on graphs could be the following:
- *Büchi Games* - There is a set $F$ given for Rajnikant and we define the set $\mathcal W=\{ \sigma \;|\; \text{inf}(\sigma) \cap F \neq \emptyset \}$
- *Muller Games* -  A set of set of final states $F$ and we define $\mathcal W = \{ \sigma\;|\; \text{inf}(\sigma) \in F\}$
- *Parity Games* - Each vertex is labelled with $n\in \mathbb{N}$. We define the set of accepting runs as $\mathcal W = \{ \sigma\; |\; \text{ minimum index in inf}(\sigma) \text{ should be even.}  \}$

---
# References
[[Arenas for Games on Graphs]]
[[Gameplay for Games on Graphs]]