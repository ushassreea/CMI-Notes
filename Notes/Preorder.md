---
aliases:
  - Quasi-Order
tags:
  - Note
alias:
---
202301270401

Type : #Note
Tags :[[Order Theory]]

---
# Preorder
```ad-note
title:
A **Preorder** relation on a set $X$ is a binary relation on $X$ denoted with $\le$ such that
- (A) $x\le x$
- (B) if $x\le y$ and $y\le z$ then $x\le z$
```

**Example:**
- Discrete Preorder $(X, =)$: $\forall x\in X, x \le x$ and if $y\ne x$ neither $x\le y$ nor $y\le x$ holds, essentially no points are comparable
- Codiscrete preorder: $\forall x, y\in X, x\le y$ (hence also $y\le x$)
- The Booleans $\mathbb B=\{\text{true, false}\}$ have a natural preorder which is $\text{true}\le\text{false}$
- Partial Orders are [[Skeletality|Skeletal]] Preorders
- A graph can by used the represent a pre order where nodes represents elements of the sets and an edge from $a$ to $b$ is equivalent to $a \le b$
- *Lexicographic Order* : $AB \sqsubseteq_{L} A AB \sqsubseteq_{L} A A A B\dots$
- *Prefix Order*: $A B \subseteq_{P}  A B A \subseteq_{P} A B A A\dots$
- *Subword Order:* $\text{HIGMAN}\preceq \text{HIGHMOUNTAIN}$ 


---
# References
[[Well-Preorder]]