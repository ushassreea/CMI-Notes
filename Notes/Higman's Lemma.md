---
tags:
  - Example
---

202311031540

tags : [[Order Theory]]

#  Higman's Lemma
---

>[!note] Higman's Lemma
>Let $\sqsubseteq$ be a [[Well-Preorder|wqo]] on $A$. Then the induced [[Monotone Domination Order]] $\preceq$ is a [[Well-Preorder|wqo]] on $A^*$

^Lemma

## Proof
The proof is by contradiction.

**FTSOC**, assume there exists bad a set of bad sequences, that is a sequence where there are no two elements in an increasing order.

Consider a minimal sequence $\{ w_{i} \}$ from the set where minimal means
- $w_{0}$ is the smallest word which starts a bad sequence
- $w_{1}$ is the smallest second-word in sequences that start with $w_{0}$
- $w_{2}$ is the smallest third word in sequences that start with $w_0, w_1$
- and so on.
This is always possible find as $\langle \mathbb{N}, \leq \rangle$ is a *well-order*.

We have no word in the sequence can be empty, as it will be trivially smaller than the next one. Hence $w_i$ can be written as $a_i\cdot z_i$ where $a_i\in A$.

Given the infinite sequence $\{ a_{i} \}_{i\in \mathbb{N}}$ we can find an increasing sub-sequence $a_{i_0} \sqsubseteq a_{i_{1}}\dots$

Using that, consider the following infinite sequence
$$
w_{0},w_{1}\dots w_{i_{0}-1},z_{i_{0}},z_{i_{1}}\dots
$$
If this sequence is a good sequence, then there are two word in increasing order which give us a pair of words in the original order that are increasing, which is a contradiction.

If this is a bad sequence, then this contradicts the minmality of the original sequence as $z_{i_0}$ is smaller than $w_{i_{0}}$ in a bad sequence that starts with $w_{0},w_{1}\dots w_{i_{0}-1}$

QED.

---
# Related
[[Well-Preorder]]
[[Monotone Domination Order]]