---
tags:
  - Note
  - Incomplete
---
202404080204

Tags : [[Infinite State Verification]]
# Well Structured Transition Systems
---
*Well Structured Transition Systems* were developed to have a generalized transition system where the existance of a well-quasi-order over the infinite set of states ensures termination of several algorithmic methods.

>[!history]
>WSTS were first proposed by Alain Finkel, his insights came from the study for Petri-nets where several decidability properties depend on monotonicity and [[Product of Well-Preorders|Dickson's Lemma]].
>Independently Abdulla et al. later proposed another definition. Their insights came from the study of lossy channel systems and some other families of infinite state autoamata.

>[!definition]
>A *Well Structured Transition System* (WSTS) is a [[Transition  System]] $\mathcal S = \langle S, \to, \leq$ equipped with a [[Preorder|Quasi-Order]] $\leq \subseteq S \times S$ between states such that the following condition holds
>- $\leq$ is a [[Well-Preorder|Well Quasi-Order]].
>- $\leq$ is compatible with $\to$, i.e. for all $s_1 \leq t_{1}$ and transitions $s_{1} \to s_{2}$, there exists a sequence of transitions $t_{1} \to^* t_{2}$ such that $s_{2} \leq t_{2}$


---
# References
