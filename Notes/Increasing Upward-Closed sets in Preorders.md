---
tags:
  - Example
---

202403261716

tags : [[Order Theory]]

#  Increasing Upward-Closed sets in Preorders
---
>[!Theorem] 
>Take any infinte increasing upward closed sets
>$$
>I_{0} \subseteq I_{1} \subseteq I_{2}\dots
>$$
>
>Then there exists an $i$ such that the sequence is constant after $i$.

For the sake of contradiction, say the sequence does not.

From each set $I_m$ for $m > 0$ pick an element $a_m$ such that $a_m \in I_m$ but $a_m \notin I_{m-1}$. If there isn't such an $a$, then we do not pick  elements.

We still infinitely many $a_i$

Consider the sequence $\{ a_{i} \}$, this is an infinite sequence where there are no $i, j$ with $i<j$ such that $a_i \sqsubseteq a_j$, which is a contradiction as this is a well-quasi order 

---
## Why do we care?

- This is nice because there is an effective way to compute the $\text {Pre}$ of a language, and the set of words has a well-quasi order.
- We can check if two upward closed sets are ==equivalent?==
- ==something??== is decidable

This gives a ==uniform?== algorithm to decide reachability. 



---
# Related
[[Well-Preorder]]
[[Equivalent Definitions of Well-preorder]].