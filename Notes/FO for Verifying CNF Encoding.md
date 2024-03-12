---
tags:
  - Example
---

202403080034

tags : [[Logic]]

#  FO for Verifying CNF Encoding
---
>[!Theorem] Lemma
>For all $h, l \in \mathbb{N}$, there is a first order sentence $\varphi_{h,l}$ of size $O(h\cdot\lg h + l)$ such that for all $n\leq T(h, l)$ and $(\gamma,\alpha)\in \text{CNF}(n)\times A(n)$.
>$$
>\mu_{h}(\gamma, \alpha) \models \alpha \models \gamma
>$$
>Furthermore, the formula can be compute in time linear to the size of the output.

^bed627

---
## Proof
The proof requires the encoding $\chi_{h,l}$ and $\chi_{last}^h$which was defined [[Lemma for Natural Number Encoding|here]].

### Literate
We first define a formula $\varphi_{h,l}^{\text{lit}}(x)$ which says that if a subword of $\gamma$ starting at $x$ is the encoding of a literal, the it satisfies $\alpha$. For that let 
$$
\begin{align}

\varphi_{h,l}^\text{lit}(x) = \exists y, x',y' &(P_{\text{val}}\ y \land \chi_{h,l}(S\ x,S\ y)\land \chi_{\text{last}}^h(S\ y,y') \land \\
&(P_{+}S\ x' \leftrightarrow P_{\text{true} }S\ y'))
\end{align}
$$
This formula can be thought of as:
- Given a literate $x$, we find $y$ which refers to its assignment.
	- $y$ is the start of a value.
	- $y$ has the same index as $x$
- Then we check that $y$ is true if and only if the literate $x$ is not negated.

### Clauses
For a clause, we just need to check that within a clause, any of the literates are satisfied, this can be done by the following formula.

$$
\varphi^{\text{clause}}_{h, l}(x) := \exists y \forall z((x < z \leq y \to \lnot P_{\text{clause}}z) \land P_{\text{lit}}y \land \varphi^\text{lit}_{h, l}(y))
$$
This formula can be read as
- $y$ is the start of a literate inside the clause starting at $x$
	- we pick a $y$ more than $x$ and for all $z$ it between them it does not denote the end of the clause
	- $y$ is the start of a literate
- $y$ is satisfied.

### CNF formulas
This part is simple, we simply need to say that all clauses are satisified
$$
\varphi_{{h, l}} := \forall y(P_{\text{clause}}y \to \varphi^\text{clause}(y))
$$
This the formula says our *CNF* formula is satisfied.

---
# Related

