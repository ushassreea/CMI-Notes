---
tags:
  - Note
  - Incomplete
---
202403251003

Tags : [[Theory of Computation]], [[Undecidability in Algebra and Topology]]
# Modular Machines
---
Modular Machines (or a $\mathbb{Z}^2$-Machine) are a class of Automata created for the purpose of solving the [[Some Problems in Computational Algebra|Word problem for Finitely Presented Groups]]. The idea was to generate a machine that would be easier to use and talk about in an environment of groups.

It is a variant of Automata that acts on $\mathbb{N}^2$ and in Turing Complete.

---

>[!definition]
>A Modular Machine is defined by a number $m\in \mathbb{N}$  and a finite set of quadruples $\{ (a, b, c, D) \}$ where
>- $0 \leq a < m$
>- $0 \leq b < m$
>- $0 \leq c < m^2$
>- $D \in \{ L, R \}$
>
>And the quadruples can be uniquely identified by just the first two components, i.e
>If $(a, b, c, D)$ is in the machine and $(a, b, c' , D')$ is in the machine then $c = c'$ and $D = D'$.

---
## Configuration and Step
As mentioned before the configuration of a Modular Machine is $(\alpha, \beta) \in \mathbb{Z}^2$ and a step in the modular machine is taken as follows.

If $\alpha = um + a$ and $\beta = vm + b$ and 
- there exists a quadruple $(a, b, c, D)$ in the Modular Machine $\mathcal M$ then
	- If $D=L$ we set $\alpha := u$ and $\beta := vm^2+c$
	- If $D=R$ we set $\alpha := um^2 + c$ and $\beta := v$.
- If there does not exist such a quadruple then we halt the Modular Machine.

>[!note]
>Because of the condition added in the definition that each quadruple in the machine is uniquely identifiable based on the first two element, and the first two elements are the ones that decided what move is to be considered, we have that these machines are deterministic.

---
# References
[[Modular Machines are Turing Complete]]