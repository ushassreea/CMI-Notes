---
tags:
  - MOC
sticker: lucide//map-pin
---
# Revisiting Complexity of First-Order and Monadic-Second-Order Logic
---
## Abstract
The model-checking problem for a logic $L$ on a class $C$ of structures asks whether a given $L$-sentence holds in a given structure in $C$. In this paper, we give super-exponential lower bounds for fixed-parameter tractable model-checking problems for first-order and monadic second-order logic. We show that unless $P = NP$, the model-checking problem for monadic-second-order logic on finite words is not solvable in time $f (k) \cdot p(n)$, for any elementary function $f$ and any polynomial $p$. Here $k$ denotes the size of the input sentence and $n$ the size of the input word. We establish a number of similar lower bounds for the model-checking problem for first-order logic, for example, on the class of all trees. 
© 2004 Elsevier B.V. All rights reserved. 

---
## Notation
- Vocabulary is given by $\tau$
- Structures are represented by $\mathcal A$
	- Universe for the structure is represented as $A$
- Tower Function $T : \mathbb{N} \times \mathbb{R}\to \mathbb{R}$
	- $T(0, r) = r$
	- $T(S(n), r) = 2^{T(n, r)}$
- Binary Size Function $L : \mathbb{N} \to \mathbb{N}$
	- $L(0) = 1$
	- $L(1) = 1$
	- $L[n] = \lfloor\lg(n-1)\rfloor+1$
	- This can also be thought of as the number of digits in the binary encoding of $n-1$
- Encoding of propositional formulas
	- All propositional variables are of the form $X_i$ for $i \in \mathbb{N}$.
	- For a set $\Theta$ of propositional variables, we done $\Theta(n)$ as the set of formulas that have variables among the following $X_0 \dots X_{n-1}$.
- The tuple $\mu_{h}(\gamma,1,\dots n-1)$ will be written as $\mu_{h}(\gamma,\star )$ for brevity.\
---
## Slides

[[Revisiting Complexity of First-Order and Monadic Second Order Logic]]

--- 
## Notes
- [[Fixed Parameter Tractibility]]
- [[Elementary Functions]]
- [[Strings in Logic]]
- [[Random Access Machines]]
	- [[Program for RAM]]
- [[Succinct Encoding of Natural Numbers Using Strings]]
	- [[Lemma for Natural Number Encoding]]
- [[Encoding for Proposition Formulas]]
	- [[FO for Verifying CNF Encoding]]
- [[Encoding of Tuples]]
- [[Complexity of Model Checking in Monadic Second Order Logic]]
	- [[Solving SAT using MSO]]
--- 
## MOCs
---
# References