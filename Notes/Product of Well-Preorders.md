---
tags:
  - Note
aliases:
  - Product of Well Quasi-Orders
  - Dickson's Lemma
---
202403261703

Tags : [[Order Theory]]
# Product of Well-Preorders
---
>[!definition] 
>Given two well-quasi orders $\langle A, \sqsubseteq_{A} \rangle$  and $\langle B, \sqsubseteq_{B} \rangle$ then we define the follow well-quasi order on $A\times B$
>$$
>(a, b) \sqsubseteq_{A \times B} (a', b') \iff a \sqsubseteq_{A} a' \land b \sqsubseteq_{B} b'
>$$

---
>[!theorem] Dickson's Lemma
>The product of two well quasi-orders is also a well quasi-order.

Given two well quasi-orders $\langle A, \sqsubseteq_{A} \rangle$  and $\langle B, \sqsubseteq_{B} \rangle$ and their product well quasi-order $\langle A \times B, \sqsubseteq_{A \times B}\rangle$ consider any infinite sequence $\{ (a_{i}, b_{i}) \}_{i\in I}$ on it.

Since $\langle A, \sqsubseteq_{A} \rangle$ is a well quasi order, we can find an infinite sub-sequence  of $\{ (a_{i}, b_{i})_{i\in I} \}$ such that projecting it onto the first coordinate gives us an increasing infinite sub-sequence. This can always be done as discussed in [[Equivalent Definitions of Well-preorder]]. Let that sequence be $\{ (a_{j}, b_{j})_{j \in J} \}$. Given that sequence we can find an infinite sub-sequence that when projected onto the second component is an increasing sequence. We call that $\{ (a_{k}, b_{k})_{k\in K} \}$. Since any two elements of the sequence are pairwise in an increasing order, so is the entire sequence.  Hence the product sequence is a [[Well-Preorder|Well Quasi-Order]].

---
# References
[[Equivalent Definitions of Well-preorder]]