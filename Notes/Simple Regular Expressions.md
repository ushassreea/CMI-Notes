---
tags:
  - Note
  - Incomplete
---
202403150903

Tags : [[Infinite State Verification]]

# Simple Regular Expressions
---

>[!quote] Some kind stranger
>Hello handsome! ;)

*SRE* over an alphabet $\Sigma = \{ a_{1},a_{2}\dots a_n \}$ is $(P_{1}+P_{2}\dots P_{m})$ where each $P_i$ are of the form $P_{i}=e_{1}^i e_{2}^i\dots e^i_{m}$ where each $e_i = (a_{j} + \epsilon)$ for some $j$.

*SRE* exactly represent regular languages that are [[Downward Closure|downward closed]].

---
## Intersection of two *SRE*s
Given two *SRE*s $P_1=e_{1}\cdot P_{1}'$ and $P_2=e_{2} \cdot P_{2}'$ 
- If $e_1 \ne e_2$ then $P_1\cap P_2=(P_{1}'\cap P_{2}) \cup(P_{1} \cap P_{2}')$
- If $e_1 = e_2$ then $P_{1} \cap P_{2} = e_{1}\cdot(P_{1}' \cap P_{2}')$

If the Language contains *Kleene Stars*
If $P_{1} = e_{1}^*\cdot P_{1}'$ then we just rewrite $P_{1} = e_{1}\cdot e_{1}^*\cdot P_{1}'$

The case where $P_1$ starts with $e_{1}^*$ is and $e_{2}=e_{1}$ then the following case changes slightly.
- If $e_1 = e_2$ then $P_{1} \cap P_{2} = e_{1}\cdot(P_{1} \cap P_{2}')$

---
# References
[[Finding the Downward Closure of Some Languages]]