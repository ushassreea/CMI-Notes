---
tags:
  - Note
  - Incomplete
---
202403111803

Tags : [[Logic]], [[Complexity Theory]]
# Complexity of Model Checking in Monadic Second Order Logic
---
>[!theorem]
>Assuming $\text{P}\ne \text{NP}$. Let  $h\in \mathbb{N}$ and $p$ be a polynomial. Then there is no algorithm $A$ for $\text{MC(MSO, }\mathbb W)$ whose running time is bounded by
>$$
>T(h, k)\cdot p(n), 
>$$
>Where $k$ is the size of the input sentence and $n$ is the size of the input word.

## The Algorithm
***INPUT:*** $\gamma \in \text{CNF}(n')$

1. Compute $\mu_{h+1}(\gamma, \star)$
2. Compute $l=\lceil \lg^{(h+1)}(n')\rceil$
3. Compute $\tilde{\varphi}_{h+1, l}$
4. Check if $\mu_{h+1}(\gamma, \star) \models \tilde{\varphi}_{h+1,l}$ using $A$.

Where $\tilde{\varphi}$ is defined in [[Solving SAT using MSO]].
### Correctness
The algorithm words only works when the logical formula is correctly above correspond to the input *CNF*, this can fail if the size of the *CNF* is to book for the *MSO* formula. But that will not be the case because

$$
n' = T(h+1, lg^{(h+1)}(n')) \leq T(h+1, \lceil lg^{(h+1)}(n')\rceil) \leq T(h+1, l)
$$

### Runtime Analysis
Without loss of generality we assume $n\leq \|\gamma \| \leq O(n^3)$. This is because we are giving a *3-CNF* formula, and the number of clauses with $3$ literals is $(2n)^3$. Hence the size of the formula is polynomial in the number of variables.

Lines  1-3 can be implemented in time polynomial in $h, n$ as shown in [[Encoding for Proposition Formulas]].

For running time of line 4, we use out algorithm $A$ that gives us time 
$$
T(h, \|\tilde{\varphi}_{h+1. l}\|) \cdot p(|\mu_{h+1, l}(\gamma, \star)|)\leq T(h, \|\tilde{\varphi}_{h+1. l}\|)\cdot p'(h, l)
$$
for some polynomial $p'$

By ![[FO for Verifying CNF Encoding#^bed627]] we have 
$$
\|\tilde{\varphi}_{h+1,l}\| \le c \cdot(h \cdot \lg h + l) \leq c\cdot(h \cdot\lg h + \lg^{(h+1)}(n')+1)
$$
We expand $l$ by line 2 of the algorithm for the last step here.

But $\lg \circ f \in o(f)$ therefore 
$$
c\cdot(h \cdot\lg h + \lg^{(h+1)}(n')+1)<\lg^h (n')
$$
forall $n'$ after some $n_{0}$.

Thus for $n'>n_{0}$ we have $T(\|\tilde{\varphi}_{h+1,l}\|)\leq T(h, \lg^{(h)}(n'))\leq n'$. Giving us time polynomial in for line 4. Making the entire algorithm polynomial in $h$ and $n'$.

This implies $3\text{-SAT}$ is in $\text P \implies \text P = \text{NP}$ which is a contradiction.
 

---
# References
[[FO for Verifying CNF Encoding]]