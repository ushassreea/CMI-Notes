---
tags:
  - Note
---
202403241003

Tags : [[Games on Graphs]]
# Winning Strategy for Reachability Games
---
## Rajnikant
For player Rajnikant, if the vertex belongs to $A_R$, it belongs to some $\mathcal A_{R}(i)$ and not in $\mathcal A_{R}(i-1)$, but it has an edge to it.
So Rajnikant chooses to go to a vertex in $A_R(i-1)$. By construction, Sreevani is forced to go to $\mathcal A_R(i-2)$. This process must terminate at $\mathcal A_R(0)$.

## Sreevani
If some vertex belongs to $\mathcal A_S$ then it does not belong to any $\mathcal A_R(i)$. 
This means it does not belong to `pre(A_R(i))`. Hence, its Rajnikant's turn, he cannot go to any $\mathcal A_R(i)$ and if its Sreevani's turn, she can choose to stay away from $\mathcal A_R(i)$. Thus the game never goes to the target node $x$.

>[!attention] Proof is omitted as its kinda trivial

---
# References
[[Winning Arena for Reachability Games]]
[[Winning Arena for Büchi Games]]
[[Winning Strategy for Büchi Games]]