---
tags:
  - Note
  - Incomplete
---
202403271203

Tags : [[Games on Graphs]]
# sigma-paradise
---
>[!Definition]
>A subset if $U$ is called a $\sigma$-*paradise* if 
>- $U$ is a $\bar{\sigma}$-trap
>- There exists a Memory-less winning strategy for $\sigma$ on $U$.

>[!attention]
>The definition of a paradise is tailor-made for omega-winning conditions and does not work well with conditions like reachability and co-reachability.

---
>[!Theorem] Lemma
>1. If $U$ is a $\sigma$-paradise, then so is $\text{attr}_{\sigma}(G, U)$.
>2. If $\{ U_{i} \}_{i\in I}$ is a family of $\sigma$-paradises. Then $\bigcup_{i\in I}U_{i}$ is also a $\sigma$-paradise

1. Given $\hat{U}=\text{attr}_{\sigma}(G, U)$ we have an attractor strategy to get to $U$ if we are not already in it. Then we just use the winning strategy for $U$.
2. For point 2
	1. If the family is finite then the procedure seems to be fairly straightforward. We give a total order to the family. This would be a priority order. To build a strategy for the union of the paradise, for each $v$ such that $v$ is in exactly one of the sets in the family then the strategy for that point would be inherited from the family member. If $v$ is in the intersection of multiple family members, then we pick the family member with the highest priority.
	2. If the family is infinite the exam same idea holds, we give a priority ordering, but for each subset of the family we must be able to figure out the member of the highest priority in that set, for that we need the order to be a [[Well Ordering]]. Such and ordering always exists because of the [[Well Ordering Principle]]. The invoking of this theorem is the only difference between the finite and the infinite case.


---
# References
[[Winning Arena for Parity Games]]