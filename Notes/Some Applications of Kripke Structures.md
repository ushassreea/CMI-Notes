---
tags:
  - Example
---

202404101253

tags : [[Logic]]

#  Some Applications of Kripke Structures
---
## Intuitionistic Logic
>[!hint] Motivation
>_Kripke Models_ reflect the following idea. From a constructive point of view, we can only assert the validity of propositions that we are sure of. But acquiring more information lets us talk about more propositions.
>
>What is known to be *True* will remain *True* forever.
>But what is not recognized as *True* today might be recognized as *True* tomorrow.
>We only assert that a proposition is *False* when we can prove that it will never be recognized as *True*.

[[Drawing 2023-09-11 12.11.46.excalidraw|Here]] is an example of a Kripke Model such that $c\Vdash\lnot\lnot(p\lor q)$ and $c\Vdash(p\to q)\to q$ but $c\not\Vdash p\lor\lnot p$ 

[[Drawing 2023-09-11 12.27.42.excalidraw|Here]] is an example of a Kripke Model where $(\lnot q\to\lnot p)\to(p\to q)$ is not proved.

[[Kripke Models are Equivalent to Heyting Algebra]]

We extend the binary relation to use it for propositions too
- $c\Vdash \varphi\land\psi$ iff $c\Vdash\varphi$ and $c\Vdash\psi$ 
- $c\Vdash \varphi\lor\psi$ iff $c\Vdash\varphi$ or $c\Vdash\psi$
- $c\Vdash \varphi\to\psi$ iff $c'\Vdash \psi$ whenever $c'\Vdash\varphi$ for all $c'\ge c$ (In the future, if we find $\varphi$, we will also, always get $\psi$ along with it)
- $c\Vdash \lnot\varphi$ if $c'\not\Vdash\varphi$ for all $c'\ge c$

For more info : [[Intuitionistic Logic]]

---
## Linear Temporal Logics
>[!hint] Intuition
>The Semantics of Linear Temporal Logic is a sequence of words where in each world some propositions are true and the temporal operators are used to talk about propositions across multiple worlds

For more info : [[Semantics for LTL]]

---
# Related
[[Linear Temporal Logic]]
[[Intuitionistic Logic]]