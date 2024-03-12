---
theme: black
height: "1200"
width: "1440"
---
The Complexity of First Order and Monadic-Second Order Logic Revisited.

presented by
Shubh and Sreevani

---

> [!note] Theorem
> Assume $P \ne NP$. Let $f$ be an elementary function and $p$ a polynomial, then there is no model checking algorithm for monadic-second order logic on the class of words whose running time is bounded by $f(k)\cdot p(n)$

note: 
- PSPACE-Complete but words >>> formula irl.
- Separate it out by considering FPT

--
### FPT
<br>
A parameterized problem is called **fixed parameter tractable** if it can be solved in the time 
$$
\begin{align}
&\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;f(k)\cdot p_k(n) \\
\text{where}\; & f \text{ is an arbitrary computable function} \\
& \quad\quad p_{k} \text{ is some polynomial.}
\end{align}
$$

 note:
 - Problem is in FPT
	 - Buchi Theorem
		 - build automata in time $f$ 
		 - word check time linear
- Still infeasible, so we want to try to bound $f$

--
> [!tip] Elementary Functions
> A function $f$ is elementary if 
> $$ \exists m, f(x)\leq 2^{2^{.^{.^{2^x}}}}$$
> where the power tower has height $m$.
> 

note:
- We show that if it not possible by contradiction
	- give an efficient encoding for CNF + tiny formula
	- fast model checking algo $\implies$ Sat can be solved in $P$

---
## Efficient Encoding for $\mathbb{N}$
note:
- CNF assignment
	- variables indexed by nats
	- find the variable of the CNF in the assignment
	- tiny formula to compare nats

--
$$
\begin{align}
\mu_{1}(0) &= \langle{1}\rangle\langle/1\rangle \\\ \mu_{1}(n) &=\langle1\rangle\ \text{bin}(n-1)\ \langle/1\rangle
\end{align}
$$

And we have the following formula that checks if two encodings of natural numbers starting at positions $x$ and $y$ are the same.

![[Pasted image 20240307162602.png]]

note:
- write formula and tell that its linear
- tell that it can check numbers of size up to $2^n$
- Motivation for general case
	- write by had $mu_2$
	- And show how easy it is to write a formula for $2^{2^n}$

--
$$
\begin{align}
\mu_{h}(n)=\langle h\rangle& \\\  &\mu_{h-1}(0)\text{ bin}(n-1)[0] \\\ &\vdots \\\ & \mu_{h-1}(d)\text{ bin}(n-1)[d] \\\ \langle / h \rangle
\end{align}
$$

And two numbers encoded by $\mu_h$ starting at positions $x$ and $y$  can be equated by the following formula.

![[Pasted image 20240307165923.png]]

note:
- show that it is of complexity $O(h+l)$
	- explain why the above statement is a lie $O(h \cdot \lg h + l)$ is the actual complexity
	- Show that we can also compute it in time linear to that.
- And that we can compare number of 2^2^...^2^l (height h)

---
## Efficient Encoding for $\mathbf{CNF}$ formulas and assignments



note:
- Write CNF definition on board
	- and of clauses

--
### Literals

$$
\mu_{h}(\lambda_{i}) = 
\begin{cases}
<\text{lit}> \mu_{h}(i)+</ \text{lit}> & \quad\lambda_{i} = X_{i} \\\ <\text{lit}> \mu_{h}(i)-</ \text{lit}> & \quad\lambda_{i} = \lnot X_{i}
\end{cases}
$$

<br>

<br>

<br>

This logical formula checks if a literal starting at position $x$ evaluates to $\top$:

![[Pasted image 20240312191113.png|1200]]

note:
mention alphabets added.

--
### Clause

$$
\begin{align}
\mu_{h}(\Delta)=\langle \text{clause}\rangle& \\\  &\mu_{h}(\lambda_{1}) \\\ &\vdots \\\ & \mu_{h}(\lambda_{m}) \\\ \langle / \text{clause} \rangle
\end{align}
$$

<br>

<br>

<br>


This formula checks if a clause evaluates to true,
i.e at least one literate in the clause that evaluates to $\top$:

![[Pasted image 20240312191210.png|1300]]

note:
mention alphabets added.


--
### CNF Formula
$$
\begin{align}
\mu_{h}(\gamma)=\langle \text{cnf}\rangle& \\\  &\mu_{h}(\Delta_{1}) \\\ &\vdots \\\ & \mu_{h}(\Delta_{m}) \\\ \langle / \text{cnf} \rangle
\end{align}
$$

<br>

<br>

<br>




This formula checks if a clause evaluates to true,
i.e at least one literate in the clause that evaluates to $\top$:

![[Pasted image 20240312191314.png|800]]

note:
mention alphabets added.

--
### Assignment Encoding

An assignment is a function from the of propositional variables to $\{\top,\bot \}$. 
For an assignment $\alpha$ we can give the following encoding to it. 

$$
\begin{align}
\mu_{h}(\alpha)=\langle \text{assn}\rangle& \\\  &<\text{val}>\mu_{h}(0) \alpha(X_{0}) <\text{/val}> \\\ &\vdots \\\ &<\text{val}>\mu_{h}(n) \alpha(X_{n}) <\text{/val}>  \\\ \langle / \text{assn} \rangle
\end{align}
$$

<br>

<br>

<br>

Now, given a input of the form $(\gamma, A): \text{CNF}(n) \times \text{Assn}(n)$ we give the following encoding.
$\mu_{h}(\gamma, A) = \mu_{h}(\gamma)\mu_{h}(A)$

--
