---
tags:
  - Note
---
202402271302

Tags : [[Logic]]
# Strings in Logic
---
For a finite string $\Sigma$, *strings* on $\Sigma$ will be structures for a vocabulary $\tau_\Sigma$ for Higher Order Logics like [[First Order Logic]] or [[Monadic Second Order Logic]]. 

The vocabulary $\tau_\Sigma$ consists of the following : 
- The $\le$ relation
- For each letter $a\in\Sigma$ we have a unary relation $P_a$.

A string $\bar{a} = a_{1}a_2\dots a_{n}$ for finite strings of just $\bar{a}=a_{1}a_{2}\dots$ for infinite strings may be represented by the structure $\mathcal S=\mathcal S(a_{1}\dots a_n)$, where:
- The universe $\mathcal S$ is the set $\mathbb{N}$ or $[n]$
- $\le^{\mathcal S}$ is the natural order on $\mathbb{N}$ or $[n]$ 
- For all $a \in \Sigma$, we have $P^\mathcal S_{a}:= \{ i\in\mathbb{N}(\text{or }[n])\quad|\quad a_{i}=a\}$ 

>[!example]
>Let $\Sigma = \{ a, b,c \}$ The following language in [[First Order Logic|FO]] represents the set of strings where each $a$ is eventually followed by a $b$.
>$$
>\forall x\big( P_{a}x\to \exists y(x \leq y\land P_{b}y)\big)
>$$

---
# References
