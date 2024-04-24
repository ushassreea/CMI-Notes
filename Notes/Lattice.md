---
tags: Incomplete
---
202308161508

Type : #Note
Tags : [[Logic]]

---
# Lattice
A *Lattice* is a partial order $\langle A, \le\rangle$ containing as top element (denoted by $1$) and a bottom element(denoted by $0$) such that every two-element subset has a:
- Least Upper Bound
	- Represented as $\inf_{A}\{a, b\}$ or $a\sqcap b$
	- Also called the _intersection_ or the _meet_
- Greatest Lower Bound
	- Represented as $\sup_A\{a,b\}$ or $a\sqcup b$
	- Also called the _union_ or the _join_
$$
\begin{matrix}a\le a\sqcup b & &a\sqcap b\le a \\b\le a\sqcup b && a\sqcap b\le b \\ c\le a,c\le b\implies c\le a\sqcap b && a\le c, b\le c\implies a\sqcup b\le c \end{matrix}
$$

>[!info] Distributive Lattices
>A lattice which satisfies
>$(a\sqcap b)\sqcup c=(a\sqcup c)\sqcap(b\sqcup c)$
>$(a\sqcup b)\sqcap c=(a\sqcap c)\sqcup(b\sqcap c)$
?is called a **Distributive Lattice**

If a lattice has $0$ and $1$, $b$ is said to be a _complement_ of $a$ if $a\sqcap b=0$ and $a\sqcup b=1$

![[Boolean Algebra#^89f0ee]]

**Heyting Algebra:**
![[Heyting Algebra#^definition]]

---
# References
[[Complete Lattice]]