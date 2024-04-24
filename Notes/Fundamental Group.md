202304031704

Type : #Note
Tags : [[Topology]]

---
# Fundamental Group
```ad-note
title:
Since the fundamental groupoid has more than one element, we can restrict our category to a single element $x_0 \in X$ called the base point, and only consider paths that go from $x_0$ to itself.
This is called the **fundamental group** of $(X,x_0)$.
```

The fundamental group is the set of homotopy classes of loops based at $x_{0}$, with a group structure on them with group operation $*$. 
It is denoted by $\Pi_{1}(X,x_{0})$.

### Proposition:
```ad-note
title:
Let $x_{0},x_{1}\in  X$ be in the same path connected component of $X$, and $\alpha$ be a path from $x_{0}$ to $x_{1}$.
Take the map $\hat{\alpha} : \Pi_{1}(X,x_{0}) \to \Pi_{1}(X,x_{1})$ $$
[f] \mapsto [\alpha]^{-1}*[f]*[\alpha]$$
is an isomorphism of groups 
```

##### Proof:
$\hat{\alpha}(a*b) = [\alpha]^{-1}*[a]*[\alpha]*[\alpha]^{-1}*[b]*[\alpha] = \hat{\alpha}(a)*\hat{\alpha}(b)$
Hence $\hat{\alpha}$ is a group homomorphism.

Denote $\beta = \bar{\alpha}$, then $\hat{\beta} : \Pi_{1}(X,x_{1}) \to \Pi_{1}(X,x_{0})$ is a group homomorphism.
So for any $[f] \in \Pi_{1}(X,x_{1})$, 
$$\hat{\alpha}(\hat{\beta}([f])) = \hat{\alpha}([\bar{\beta}]*[f]*[\beta]) =[\bar{\alpha}]*[\bar{\beta}]*[f]*[\beta]*[\alpha] = [f]$$ (since $[\alpha] = [\beta]^{-1}$)
Similarly $\hat{\beta} \circ \hat{\alpha} = id$.

### Corollary 1:
```ad-note
title:
For a path connected space $X$, the fundamental group is independent of the base point.
```

### Corollary 2:
```ad-note
title:
A loop $f$ at $x_0$ induces an automorphism $\hat{f}$ of $\Pi_1(X,x_0)$.
```

---
# $\Pi_{1}$ as a functor
```ad-info
Consider the category of _pointed topological spaces_, with objects $\{(X,x_0)\}$ ordered pairs of topological spaces $X$ and the choice of base point $x_0 \in X$.
The morphisms are given by continuous functions that take base points to base points.
$$ f:(X,x_0) \to (Y,y_0)$$
where $f$ is cts and $f(x_0) = y_0$.
```

### Lemma:
```ad-note
title:
Any morphism of pointed topo spaces $h : (X,x_{0}) \to (Y,y_{0})$ induces a group homomorphism $h_{*} : \Pi_{1}(X,x_{0}) \to \Pi_{1}(Y,y_{0})$ defined by $$
h_*([f]) := [h \circ f]
$$
```
##### Proof:
Note that $h_{*}$ is well defined. If $f \simeq_{p} f'$ then $h \circ f \simeq_{p} h \circ f'$. 
$h_{*}([f]*[g]) = h_{*}([f*g]) = [h \circ (f*g)] = [(h \circ f)*(h \circ g)] = [h \circ f] *[h \circ g] = h_{*}([f])h_{*}([g])$

### Lemma:
```ad-note
title:
$\Pi_1$ is a functor from the category of pointed topo spaces to Groups
```
##### Proof:
It takes $(X,x_{0})$ to $\Pi_{1}(X,x_{0})$ and $f : (X,x_{0}) \to (Y,y_{0})$ to $f_{*}$.
Let $g : (Y,y_{0}) \to (Z,z_{0})$.
To show that composition is preserved, we need to show that $\Pi_{1}(f \circ g) = f_{*} \circ g_{*}$.
$\Pi_{1}(f \circ g)[\alpha] = (f \circ g)_{*}([\alpha]) = [f \circ g\circ\alpha] = f_{*}(g_{*}([\alpha]))$. 

To show that identity is preserved, we need to show that for $id : (X,x_{0}) \to (X,x_{0})$
$\Pi_{1}(id) = id_{\Pi_{1}(X,x_{0})}$
$$
\Pi_{1}(id)[\alpha] = [id \circ \alpha] = [\alpha]
$$
Hence we are done.

#### NOTE: functors carry isomorphisms to isomorphisms, and hence we have the following:
### Corollary:
```ad-note
title:
If $h : (X,x_0) \to (Y,y_0)$ is a homeomorphism, then $h_{*} : \Pi_1(X,x_0) \to \Pi_1(Y,y_0)$ is an isomorphism.
```

---
# Examples
1. $S ^{1}$ has fundamental group $\mathbb{Z}$.

---
# References
[[Fundamental Groupoid]]
[[Homotopy of paths]]
[[Category Theory]]
[[Groups]]
[[Homotopy Group]]
[[Fundamental Group]]
[[Continuous Functions]]
[[Homeomorphisms]]
[[S^1]]

