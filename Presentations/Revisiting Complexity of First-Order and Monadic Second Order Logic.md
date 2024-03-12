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
		 - build automata in time f 
		 - word check time linear
- Still infeasible, so we want to try to bound f

--
> [!tip] Elementary Functions
> A function $f$ is elementary if 
> $$ \exists m, f(x)\leq 2^{2^{.^{.^{2^x}}}}$$
> where the power tower has height $m$.
> 

note:
- We show that if it not possible by contradiction
	- give an efficient encoding for CNF + tiny formula
	- fast model checking algo -> Sat can be solved in P

---
## Efficient Encoding for $\mathbb{N}$
note:
- 1st check if given assn does it sat cnf.
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
- tell that it can check numbers of size up to 2^n
- Motivation for general case
	- write by had mu_2
	- And show how easy it is to write a formula for 2^2^n

--
$$
\begin{align}
\mu_{h}(n)=\langle h\rangle& \\\  &\mu_{h-1}(0)\text{ bin}(n-1)[0] \\\ &\vdots \\\ & \mu_{h-1}(d)\text{ bin}(n-1)[d] \\\ \langle / h \rangle
\end{align}
$$

And two numbers encoded by $\mu_h$ starting at positions $x$ and $y$  can be equated by the following formula.

![[Pasted image 20240307165923.png]]

note:
- the complexity to compute mu_{h} (n) is O(h * lg(lg n) )
- show that  the size of formula is $O(h+l)$
	- explain why the above statement is a lie O(h *lg h + l) is the actual size
	- Show that we can also compute it in time linear to that.
- And that we can compare number of 2^2^...^2^l (height h)

--
### auxiliary functions used
![[Pasted image 20240307163144.png]]


---
## Efficient Encoding for $\mathbf{CNF}$ formulas and assignments



note:
- Write CNF definition on board
	- and of clauses

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

Given a input of the form $(\gamma, A): \text{CNF}(n) \times \text{Assn}(n)$ we give the following encoding.
$\mu_{h}(\gamma, A) = \mu_{h}(\gamma)\mu_{h}(A)$

We build a logical formula that checks if the assignment satisfies the CNF formula.

note:
mention alphabets added.
later we'd like to say there exists an assignment that satisfies a given CNF.


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

$\begin{align}
\varphi_{h,l}^\text{lit}(x) = \exists y, x',y' &(P_{\text{val}}\ y \land \chi_{h,l}(S\ x,S\ y)\land \chi_{\text{last}}^h(S\ y,y') \land \\\  &(P_{+}S\ x' \leftrightarrow P_{\text{true} }S\ y'))
\end{align}$


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

$$\varphi^{\text{clause}}_{h, l}(x) := \exists y \forall z((x < z \leq y \to \lnot P_{\text{/clause}}z) \land P_{\text{lit}}y \land \varphi^\text{lit}_{h, l}(y))$$

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

$$
\varphi_{{h, l}} := \forall y(P_{\text{clause}}y \to \varphi^\text{clause}(y))
$$

We have, \
$\mu_{h}(\gamma, \alpha) \models \varphi_{h+1, l} \iff \alpha \models \gamma$ 

note:
mention alphabets added.
mu_{h}(gamma, alpha)$ can be computed in O(h * lg^2 n * (| gamma | + n))
phi is of size O(h * lg h + l) computed in the same.

---

### MSO formula for existence of a satisfying assignment

We want to keep the structure of an assignment to check for satisfiability. For this, we assign all variables to a symbol say $\star$ 


$$
\begin{align}
\mu_{h}(\star)=\langle \text{assn}\rangle& \\\  &<\text{val}>\mu_{h}(0) \  \star <\text{/val}> \\\ &\vdots \\\ &<\text{val}>\mu_{h}(n) \ \star <\text{/val}>  \\\ \langle / \text{assn} \rangle
\end{align}
$$

<br>
<br> 

We now want an MSO formula that checks if $\gamma $ is satisfiable. 


<br>

$\tilde{\varphi}_{h, l} = \exists X(\forall x(x \in X \to P_{\star} x) \land \varphi'_{h, l})$

Where $\varphi'_{h, l}$ is the formula obtained by replacing $P_{\text {true}}$ with $X$ in $\varphi_{h, l}$. \
We now have,

$\mu_{h}(\gamma, \star) \models \tilde{\varphi}_{h+1, l} \iff \gamma \text{ is satisfiable.}$  

note:
the X represents the set of vars that are assigned true. 
And we check if there possible X

---

> [!note] Theorem
> Assume $P \ne NP$. There is no model checking algorithm for monadic-second order logic on the class of words whose running time is bounded by $T(h, k)\cdot p_{h}(n)$.


--
### Poly-time algorithm for 3-SAT

***INPUT:*** $\gamma \in \text{CNF}(n')$

1. Compute $\mu_{h+1}(\gamma, \star)$ 
2. Compute $l=\lceil \lg^{(h+1)}(n')\rceil$
3. Compute $\tilde{\varphi}_{h+1, l}$
4. Check if $\mu_{h+1}(\gamma, \star) \models \tilde{\varphi}_{h+1,l}$ using $A$.

note: 
gamma is poly in n as we are dealing with 3-Sat. so max of O(n^3).
now, steps 1,2,3 are poly in n
(for our ref
-  \mu_{h}(\gamma, \alpha) can be computed in O(h *lg^2 n * (|gamma | + n))
	- the complexity to compute mu_{h}(n) is O(h *lg^2 n )
- phi {h+1, l} is of size O(h *lg h + l) computed in the same.

--

#### Computation time of Step 4  

$$T(h, \|\tilde{\varphi}_{h+1. l}\|) \cdot p(|\mu_{h+1, l}(\gamma, \star)|)\leq T(h, \|\tilde{\varphi}_{h+1. l}\|)\cdot p'(h, l)$$

by our assumption that Model-Checking for MSO can be done in \
$T(h, k)\cdot p_{h}(n)$.

For a large enough $n'$ we have,
$\| \tilde{\varphi}_{h+1,l} \| \le c \cdot(h \cdot \lg h + l) \leq c\cdot(h \cdot\lg h + \lg^{(h+1)}(n')+1)<\lg^{(h)} (n')$. 
<br>

Thus for $n'>n_{0}$ we have $T(\|\tilde{\varphi}_{h+1,l}\|)\leq T(h, \lg^{(h)}(n'))\leq n'$. 
 
Hence, step 4 is also polynomial in $n'$.

note: 
|mu_{h+1, l}(\gamma, \star)| is poly as we saw before.
last ineq because log grows faster that log^2
Hence, we get P = NP.

---

> [!note] Theorem
> Assume $P \ne NP$. Let $f$ be an elementary function and $p$ a polynomial, then there is no model checking algorithm for monadic-second order logic on the class of words whose running time is bounded by $f(k)\cdot p(n)$ 

note:
we are done:)