---
tags:
  - Note
  - Incomplete
---
202311081411

Tags : [[Advanced Algorithms]]

---
# Network Reliability
**Given:** $G=(V,E)$ undirected, each edge can fail with probability $p$, independent of other edges
**Goal:** To compute $p_{\text{fail}}$, i.e. the probability that $G$ gets disconnected

---

This problem is *\#P complete*.
*\#P complete:* Class of functions that count the number of solutions to a problem in NP (harder than NP), eg, \#perfect matchings, \#SAT

```ad-note
title: **FPRAS: (Fully Polytime Randomized Approximation Scheme)**
Given $(G,p,\epsilon)$, an FPRAS is a polytime algorithm that outputs a value $z$ st $Pr[(1-\epsilon)p_{\text{fail}}\leq z\leq(1+\epsilon)p_{\text{fail}}]\geq \frac{3}{4}$.

*Note:* There is no FPRAS for the counting version of NP-complete problems.
```

---

**Network reliability:** Counting the total weight of disconnected subgraphs of $G$, where weight of a subgraph $H$ that has $|E|-r$ edges is $p^{r}(1-p)^{|E|-r}$.
How do we do this?

```ad-tip
title: Inspiration: Unbiased estimator
There are regions in space $R\subseteq U$. We want to estimate $\frac{|R|}{|U|}$. We will throw darts at the entire region with uniform probability and compute the number of darts that land in $|R|$. But this will require throwing a lott of darts if the region is very small. So we will need to do work to see what values this works for. Which is what we will do now.
```

Do $i=1,\dots,t$ times:
Find a random subgraph of $G$ by choosing each edge with $(1-p)$. Set $X_{i}=1$ iff the subgraph is disconnected.

$X= \dfrac{1}{t}\sum X_{i}$
$\mathbb{E}[X_{i}]=Pr[X_{i}=1]=p_{\text{fail}}$(??)
$\mathbb{E}[X]=p_{\text{fail}}=\mu$
By Chebyshev's inequality,
$Pr[]$ 
idk random calculations

---
**Idea:** $p_{\text{fail}}\geq p^{c}$ where $c$ is the size of a minimal cut in $G$.

- If $p^{c}\geq \frac{1}{n^{4}}$, we pick random subgraphs of $G$ $O\left( \frac{n^{4}}{\epsilon^{2}} \right)$ times. (Each edge is picked with probability $(1-p)$.)
- If $p^{c}< \frac{1}{n^{4}}$,
1. Find $\alpha$ s.t. $Pr[\text{a cut of size }\geq\alpha c \text{ fails}]\leq\epsilon p^{2}$.
2. Number of cuts of size $\leq\alpha c$ is at most $n^{2\alpha}$. Call them *'small'* cuts.
3. Enumerate all small cuts with probability $\geq 1-\delta$.
4. Estimate failure probability of small cuts.
---
Let $C_{1},C_{2},\dots,C_{m}$ be 'small' cuts in $G$.
$C_{i}=\{ e_{i_{1}},\dots,e_{i_{r_{i}}} \}$
$Pr[\bigvee\limits_{i=1}^{m} C_{i}\text{ fails}]=Pr[\bigvee\limits_{i=1}^{m}(x_{e_{i_{1}}}\land x_{e_{i_{2}}}\land\dots \land x_{e_{i_{r_{i}}}})=1]$,
where each $x_{j}=1$ with probability $p$.
We consider the case where $p=\frac{1}{2}$.

For $p=\frac{1}{2}$, $n=$ number of variables, $m=$ number of terms
DNF formula (Disjunction Normal Form) $\phi=\bigvee\limits_{i=1}^{m}(x_{e_{i_{1}}}\land x_{e_{i_{2}}}\land\dots \land x_{e_{i_{r_{i}}}})$, each 'clause' is called a term here.
$Pr[\phi=1]=\dfrac{\text{\# satisfying assignments to }\phi}{2^{n}}$

Counting \#$\phi$:
$S_{i}=$ set of satisfying assignments for the $i^{th}$ term
$l_{i}=$ \# of literals in the $i^{th}$ term
$|S_{i}|=2^{n-l_{i}}$
\#$\phi=|\bigcup\limits_{i=1}^{m}S_{i}|$ 

```ad-failure
title: The numerator is too small compared to the denominator(??)
```

```ad-hint
title: [Karp-Luby '83'] **Importance Sampling:**
**Idea:** To choose a smaller sample space and pick many random assignments from it.
Let $a_{1},\dots,a_{s}$ be satisfying assignments.
Sample space: $U=\{ (a,i)\ | \text{ assignment }a \text{ satisfies the }i^{th} \text{ term} \}$
Call $(a,i)\in U$ *special* if $i=\min\{ i'\ |\ (a,i)\in U \}$. We want to estimate $\dfrac{\text{\# special elements in U}}{|U|}$. Number of special elements $=s=\#\phi$
We can make an $m\times s$ grid of $S_{i}\times a_{j}$.

**Sampling:**
Select a term $i$ with probability $\dfrac{|S_{i}|}{|U|}$.
Select a uniformly random assignment that satisfies $i^{th}$ term.
$|U|=\sum\limits_{i=1}^{m}|S_{i}|$.
Number of samples required $=\dfrac{4m}{\epsilon^{2}}$.
```

---
3. Enumeration of small cuts:
Execute Karger's algorithm $r$ times.
Output the cut if it is a cut of size $\leq\alpha c$ different from the previously output cuts.

```ad-tip
title: Motivation
We will let $r$ be variable. We want to find how many times we need to execute Karger's algorithm to enumerate all small cuts. So we will calculate the probability that a particular cut is not output after $r$ times.
```

$Pr[\text{a cut }C,|C|\leq\alpha c,\text{ is output}]\geq \dfrac{1}{n \choose {2\alpha}}\approx \dfrac{1}{n^{2\alpha}}$. ($\theta=n^{2\alpha}$)
$Pr[C\text{ is never output}]\leq\left( 1-\frac{1}{\theta} \right)^{r}\leq e^{\frac{-r}{\theta}}$
We want $e^{\frac{-r}{\theta}} \leq \frac{\delta}{\theta }$.
$r\geq\theta\left( \log\theta+\log \frac{1}{\delta} \right)$.

---
1. Find $\alpha$ s.t. $Pr[\text{a cut of size }\geq\alpha c \text{ fails}]\leq\epsilon p^{2}$.
$p^{c}=n^{-(4+\beta)}$
Let $C_{1},C_{2},\dots$ be large cuts with sizes $c_{1}\leq c_{2}\leq\dots$.
Consider the first $n^{2\alpha}$ cuts.
$$
\begin{align*}
Pr[\text{any of the first }n^{2\alpha}\text{ cuts fails}]&\leq n^{2\alpha}.p^{\alpha c}\\
&= n^{2\alpha-(4+\beta)\alpha}\\
&= n^{-(2+\beta)\alpha}
\end{align*}
$$

Number of cuts of size $\leq\gamma c$ is at most $n^{2\gamma}$.


stuff


---
# References
