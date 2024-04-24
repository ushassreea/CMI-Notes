---
tags:
  - Note
  - Incomplete
---
202404031204

Tags : [[Logic, Automata and Games]]
# Small  Progress Measures
---
>[!idea]
$\sigma$ is a strategy for Rajnikant closed on $W$. $\sigma$ is winning for Rajnikant iff all simple cyclies in $G$ restricted to omega have minimum element even.

>[!definition] Parity Progress Measure
  >Consider $u_1, u_2 \in \mathbb{N}^d$ and let $\le$ be the lexicographical order and let $\le_i$ be the comparison of the elements restricted to the first $i$ components.
    >Let $G$ be a parity garph, then a function $\rho$ from the set of vertices to $\mathbb{N}^d$ is a parity progress measure for $G$ if for all edges $(v, w) \in E$, we have $\rho(v) \ge_{p(q)} \rho(v)$ and the inequality is strict if $p(v)$ is odd.

>[!Theorem] Lemma
>If there is parity progress measure for a parity graph $G$, then all cycles in $G$ are even.

**Proof:**
If there is an odd cycle, then we look at the last instance of the smallest element with value $i$, then we can say that the first $i$ components are never increased, and whenever we visit such elements, then the first vector derived from the first $i$ components strictly drops. If it is in a cycle, we can take it infinitely many times, but that is a contradiction as the set is well ordered.

The converse is also true.
>[!theorem] Lemma
>If all cycles are even then there exists a parity progress measure $\rho: V \to M_{G}$ for $G$.

**Proof:**
By induction of $|V|$ we will prove that if $p(v)$ is odd, then $\rho(q) >_{p(q)} \bar{0}$.

For the base if the set of vertices is non-empty, then if the set of Rajnikant vertices is non-empty, we set the parity progress measure for $G \setminus V_R$. We set $rho(q) = \bar{0}$ orall all $q in $V_R$


---
# References
