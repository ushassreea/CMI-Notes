---
tags:
  - Example
---

202403140229

tags : [[Algebra]], [[Theory of Computation]]

#  Conjugation Problem on a Free group
---
>[!error] Question
>Given a group $G = \langle S| \emptyset \rangle$ and words $w$ and $v$ on the alphabet $S$, does there exists a $g\in G$ such that $w = g v g^{-1}$. 

---

## Algorithm
- Reduce both the words to [[Cyclically Reduced Term|cyclically reduced forms]].
- Check $w'$ is a cyclic permutation of $v'$ where $w'$ and $v'$ are cyclically reduced forms of $w$ and $v$.

## Proof of Correctness
- $w$ and $v$ are conjugates, iff their reduced forms are conjugates
	- Same $g$ works in both cases
- Assume both are in reduced from. $w$ and $v$ are conjugates iff their cyclically reduced forms are conjugates.
	- the cyclic parts removed can be used to construct a $g$ in one cases to another.
- Assume both are in cyclically reduced form, then $w$ and $v$ are conjugates of each other iff they are cyclic permutations of each other.
	- if they are cyclic permutations then its trivial to find a $g$, as a cyclic permutation that shifts characters by 1 space is just conjugation with $g$ = first element.
	- If they are conjugates of each other, then guess a $g$, We know that $g v g^-1$ reduced to a cyclically redced form, therefore either $g$ is identity, $g$ is consumed entirely while reducing. In both scenarios we get a cyclic permutation of $v$

---
# Related
[[Some Problems in Computational Algebra]]
[[Cyclically Reduced Term]]
[[Free Group]]