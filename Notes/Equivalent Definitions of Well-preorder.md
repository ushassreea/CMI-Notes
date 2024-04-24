---
tags:
  - Example
  - Incomplete
---

202403201145

tags : [[Order Theory]]

#  Equivalent Definitions of Well-preorder
---
>[!tip] The following are equivalent
>1. $(A, \leq)$ is a well quasi-order
>1. Given any infinite sequence of elements in $A$, there is always an infinite increasing sub-sequence of it.
>1. There are no infinite descending chains and no infinite anti-chains.

---
## Proofs
### $1 \to 2$
Let $\{ a_{n} \}_{n \in I}$ is an infinite sequence in a *well quasi order*. 
Consider all element of the sequence that satisfy the following predicate,
$$
P\;a_{i} := \forall j, j >i \to a_{j} \not\ge a_{i}
$$
That is, all elements that are not dominated by another element after it.

Since there are no infinite increasing sub sequences, we have that infinitely many elements satisfy the proposition. 

Consider the infinite sub-sequence consisting of all the elements in $\{ a_{n} \}$ that satisfy the predicate.

Since this an infinite sequence on a well quasi order $\exists x\;y,x<y \land a_x \sqsubseteq a_y$ which is a contradiction.

### $2 \to 3$
The proof is by contradiction and is trivial. 
Consider an infinite sub-sequence $S$ of the original sequence that is strictly descending or is an anti-chain.

By $2$ we have that it contains an increasing sub sequence, which is a contradiction.

### $3 \to 1$
The proof has a similar flavour to the proof for $1 \to  2$.

We start with the following predicate
$$
P \ a_{i} := \forall j, j > i \to a_{j} \not\sqsubset a_{i}.
$$
Since we know that there are no infinite descending chains, there would be infinitely many such elements that satisfy this property.

Given the predicate, we know that there are no two elements in decreasing order.

Consider the sub-sequence of elements that satisfy the predicate.
From our assumption, we have that this is not an anti-chain, hence there must exist a pair of indices $i, j$ such that $i < j$ and $a_i \sqsubseteq a_j$.

---
# Related
[[Well-Preorder]]
[[Increasing Upward-Closed sets in Preorders]]