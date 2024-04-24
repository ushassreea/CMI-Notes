---
tags:
  - Note
  - Incomplete
---
202403301403

Tags : [[Group Theory]]
# HNN - Extensions
---
>[!cite] 
>In their 1949 paper, Graham Higman, Bernhard Neumann and Hanna Neumann 

>[!Theorem]
>Let $G$ be a group. Let $H, K$ be two subgroups of $G$ such that $H\cong K$ and let $\phi : H \to K$ be an isomorphism, then there exists a supergroup $G'$ of $G$ and $p\in G'$ such that $\phi(h) = p^{-1} h p, \forall h \in H$

The above group has can be given the following [[Presentation of a Group|presentation]]
$$
G' = \langle G, p_{i}, i \in I \;|\;p_{i}^{-1} h p_{i} = \phi_{i}(h), h \in H_{i}, i \in I \rangle
$$
and is called the HNN-Extension of $G$ with stable letter $p_i$ associated with subgroups $H_i$ and $K_i$.

---
# References
[[Britton's Lemma]]