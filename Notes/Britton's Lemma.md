---
tags:
  - Example
---

202404021136

tags : [[Group Theory]]

#  Britton's Lemma
---
>[!theorem] Lemma
>Let $w$ be a word in $G \cup \{p\}$ containing some stable letter $p$ or $p^-1$. If $w = 1_G$ then $w$ contains a pinch.

>[!definition] Pinch
>A Pinch is a word of the form $p^{-1} h p$ or $p k p^{-1}$ where $p$ is a stable letter and $h \in H, k \in K$.

>[!theorem] Corollaries for Britton's Lemma
>- If $G'$ is an [[HNN - Extensions]] of $G$ then $G$ embeds in $G'$, i.e, the canonical homomorphism $\phi : G \to G'$ that is injective.
>- A good subgroup of $G$ is $A \subseteq G$ if $\phi(A \cap H_{i}) = A \cap K_{i}$ for all $i\in I$. That is $A$ plus the stable letters form an HNN extension $A'$ such that $A' \cap G = A$
>- In a group $\langle G, p \; | \; p^{-1} h p =\phi(h)=h, h\in H\rangle$ where the isomorphism is identity, then we have $p^{-1} g p = g \iff g\in H$. 


---
# Related
- [[HNN - Extensions]]