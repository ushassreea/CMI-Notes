---
tags:
  - Example
---

202404031633

tags : [[Undecidability in Algebra and Topology]]

#  Proof for the Undecidability of the Word Problem
---
>[!theorem]
>There is a finitely presented group for which the word problem is *unsolvable*

For a Proof Sketch, read [[Word Problem for Finitely Presented Groups is Undecidable]].

---
## Modular Machine Encoding in Groups
First we define a the group $G$ to encode configurations of the modular machine $\mathcal M$.
$$
G = \langle x, y, t\;|\; xy =yx \rangle \cong \mathbb{Z} * \mathbb{Z}^2
$$
Here the group is isomorphic to a product of 
- $\mathbb{Z}^2$ to encode the the configurations of the modular machine, $x, y$ are the corresponding elements.
- $\mathbb{Z}$ for algebraic manipulation, $t$ is the corresponding element.
### Encoding a configuration
For every $(\alpha, \beta)$ we have the following element in $G$ : $t(\alpha, \beta) = x^{-\alpha} y^{-\beta} t x^\alpha y^\beta$ and we construct the following group w those as generators

$$
G > T = \langle t(\alpha, \beta)\; | \;\alpha,\beta \in \mathbb{Z}^2)
$$

To make dealing with dealing with transitions easier we also define
$$
G \geq G^{MN}_{ab} = \left\langle t(a, b), x^M, y^N\right\rangle
$$
The idea is similar to to having a base $M$ and base $N$ encoding of the components of the configuration with $a$ and $b$ as the least significant digits. The above explanation also hits that these are more than just the set of all "valid" encodings of the configuration, but that is okay because we only deal with the ones used in transitions.

### Encoding Transitions

>[!note]
>If a pair of configurations are "connected" by a transition, then their corresponding groups are ismorphic

For the right transition $\{ (a, b, c, R) \}$ in $\mathcal M$ we have a canonical isomorphism between $\phi_{(a, b, c, R)} : G_{ab}^{MM} \to G_{c{0}}^{M^21}$ defined as
$$
t(a,b) \mapsto t(c,0)\quad,\quad x^M \mapsto x^{M^2}\quad,\quad y^M \mapsto y
$$

Similarly we define isomorphisms for transitions of $\mathcal M$.

We now define $G_\mathcal M'$ as the [[HNN - Extensions|HNN-extension]] of $G$ incorporating the all the above isomorphism

### Ending Configurations
$$
T_{M} = \langle t(\alpha,\beta) | (\alpha,\beta) \in H_{\mathcal M} \rangle
$$
We have 
![[Word Problem for Finitely Presented Groups is Undecidable Lemma 1#^17831a]]

So we also have $T_M'$ which is an HNN-Extension of $T_M$ as discussed in [[Britton's Lemma]]

---
# Related
[[Word Problem for Finitely Presented Groups is Undecidable]]
[[Word Problem for Finitely Presented Groups is Undecidable Lemma 1]]
[[Britton's Lemma]]