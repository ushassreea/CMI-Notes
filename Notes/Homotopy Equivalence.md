202304041604

Type : #Note
Tags : [[Topology]]

---
# Homotopy Equivalence
```ad-note
title:
Let $f : X \to Y$ and $g : Y \to X$ be cts maps. If $g \circ f : X \to X$ is homotopic to $id_{X}$ and $f \circ g : Y \to Y$ is homotopic to $id_{Y}$, then we say that $f,g$ are **homotopy equivalences**. $X$ and $Y$ have the same **homotopy type**.
```
#### Examples:
1. If $r : X \to A$ deformation retract, $f = r$, $g = i : A \hookrightarrow X$
2. $A =$ figure eight space, $X = \mathbb{R}^{2} \setminus \{ 2 \ points \}$, $(i,r)$ maps
   $A' =$ Theta figure $(i',r')$ maps
   $$
A \xrightarrow{i} X \xrightarrow{r'} A' \xrightarrow{i'} X \xrightarrow{r} A
$$
This is homotopic to $A \xrightarrow{i} X \xrightarrow{r}A$ because $r' \circ i'$ is homotopic to $id_{X}$. So $r \circ i$ is homotopic to $id_{A}$ and similarly in the other direction.
So, $A,A'$ are homotopy equivalent with $f = r' \circ i$ and $g = r \circ i'$.

### Proposition:
```ad-note
title:
If $f:X \to Y$ and $g:Y \to Z$ are homotopy equivalences then $g \circ f:X\to Z$ is a homotopy equivalence.
```
##### Proof:
Take 
$$
X \xrightarrow{f} Y \xrightarrow{g} Z \xrightarrow{g'} Y \xrightarrow{f'} X
$$
This is homotopic to $id_{X}$. So $X$ and $Z$ are homotopy equivalent with $g \circ f$ and $f' \circ g'$ as the homotopy equivalence maps.

### Definition:
```ad-note
title:
$X$ is contractible if $id_X$ is homotopic to a constant map $X \to \{p\}$, $p\in X$.
```
This gives that $\{ p \}\to X$ is a homotopy equivalence.

### Theorem:
```ad-note
title:
Let $f : (X,x_0)\to (Y,y_0)$ be a cts map. If $f$ is a homotopy equivalence, then $f_*$ is an isomorphism.
```
##### Proof:
Recall Lemma 2 from [[Deformation Retracts]].
Let $g : Y \to X$ be the homotopy inverse to $f$. Let $g(y_{0}) = x_{1}$ and let $f(x_{1}) = y_{1}$.
Consider the sequence of maps 
$$
(X,x_{0}) \xrightarrow{f} (Y,y_{0}) \xrightarrow{g} (X,x_{1}) \xrightarrow{f} (Y,y_{1})
$$
This gives rise to the following homomorphisms: 
$$
\Pi_{1}(X,x_{0}) \xrightarrow{f_{*}} \Pi_{1}(Y,y_{0}) \xrightarrow{g_{*}} \Pi_{1}(X,x_{1}) \xrightarrow{f_{*}'} \Pi_{1}(Y,y_{1})
$$
Since we know that $g \circ f$ is homotopic to $id_{X}$, so by the lemma applied to $h = g \circ f$ and $k = id_{X}$, we get that $h_{*} = \hat{\alpha}(k_{*}) \implies (g \circ f)_{*} = \hat{\alpha}(id_{\Pi_{1}(X,x_{0})}) = \hat{\alpha}$.
Which means that $g_{*} \circ f_{*}$ is an isomorphism.

Similarly, $f \circ g$ is homotopic to $id_{Y}$ and so the lemma gives that $f_{*}' \circ g_{*}$ is an isomorphism, this gives that $g_{*}$ is bijective, and hence an isomorphism. Which gives that $f_{*}$ is an isomorphism.


---
# References
[[Homotopy of paths]]
[[Deformation Retracts]]
[[Fundamental Group]]


