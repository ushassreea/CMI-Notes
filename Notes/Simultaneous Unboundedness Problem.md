---
tags:
  - Example
---

202403151015

tags :  [[Infinite State Verification]]

#  Simultaneous Unboundedness Problem
---
Given a language $L$ and $u_0,u_{1},v_{1},u_{2},v_{2}\dots u_{n},v_{n} \in \Sigma^*$ then is the following true: $\forall k\in \mathbb{N}$ there exist $k_{1}\dots k_n>k$ such that $u_{0}v_{1}^{k_{1}}u_{1}v_{2}^{k_{2}}\dots u_{n}v_{n}^{k_{n}} \in L$. 

>[!question] Claim
>For a nice enough class of languages, *SUP* if and only if
>$$
>
>(L \cap u_{0}v_{1}^{k_{1}}u_{1}v_{2}^{k_{2}}\dots u_{n}v_{n}^{k_{n}})\downarrow = u_{0}\downarrow (\Sigma v_{1})^{k_{1}}u_{1}\downarrow (\Sigma v_{2})^{k_{2}}\dots u_{n}\downarrow (\Sigma v_{n})^{k_{n}}
>$$
---
# Related
