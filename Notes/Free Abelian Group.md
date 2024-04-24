202306041006

Type : #Note
Tags : [[Algebra]]

---
# Free Abelian Group
```ad-note
title:
A free abelian group of rank $n$ is any group which is the direct sum of $n$ subgroups, each of which is isomorphic to $\mathbb{Z}$, equivalently, it is isomorphic to the additive group $\mathbb{Z}^{n}$.
```

The rank of such a group is well defined because the $\mathbb{Z} ^{n}$'s are pairwise non isomorphic.
### Proposition 1:
```ad-note
title:
$\mathbb{Z}^{n} \simeq \mathbb{Z}^{m}$ iff $m = n$.
```
###### Proof:
Let $m < n$ and let there be an isomorphism $\phi : \mathbb{Z}^{m} \to \mathbb{Z}^{n}$, let $A$ be the corresponding matrix for this map.
Let $\widetilde{\phi} : \mathbb{Q}^{m} \to \mathbb{Q}^{n}$ be the map corresponding to $A$ but on $\mathbb{Q}^{m}$.
Then since $m < n$, this map is not injective, thus there is a vector $v \in \mathbb{Q}^{n}$ which has no preimage.
Scaling the vector $v$, we get that there is a vector in $\mathbb{Z}^{n}$ which has no preimage, hence the map $\phi$ is not injective, that's a contradiction.

### Proposition 2:
```ad-note
title:
Any subgroup of a free abelian group of rank $n$ is free of rank $\le n$.
```
###### Proof:
WLOG, let $G = \mathbb{Z} \oplus \mathbb{Z} \oplus \dots \oplus \mathbb{Z}$ (n times). We will show by induction that $H$ is free of rank $\le n$.
For $n = 1$, we know any subgroup of $\mathbb{Z}$ is just $m\mathbb{Z}$ for some $m$, in this case we are done.
Let it hold for $n-1$.
Then let $\pi : G \to \mathbb{Z}$ be the projection onto the first coordinate, let $K$ be the kernel of this map.
$K \simeq \mathbb{Z}^{n-1}$. Thus $H \cap \mathbb{Z}^{n-1}$ is free of rank $\le n-1$.
Now $\phi(H)\subset \mathbb{Z}$ is either $\{ 0 \}$ or infinite cyclic. If it is $\{ 0 \}$, then $H = H \cap K$ and we are done.
Otherwise, $\phi(H) = (\pi(h))$ for some $h \in H$, we will show that $H = \mathbb{Z}h \oplus (H\cap K)$.

Let $x \in H$ be any element, then $x = \frac{\pi(x)}{\pi(h)}h + (x- \frac{\pi(x)}{\pi(h)}h)$
The first term is in $\mathbb{Z}h$, and the second one is in $H \cap K$, thus $H = \mathbb{Z}h \oplus (H \cap K)$ (since it is easy to see that $\mathbb{Z}h \cap H \cap K = \{ 0 \}$).

### Proposition 3:
```ad-note
title:
Let $G,H$ be two free abelian groups of rank $n$ with $H \subset G$, then $G /H$ is a finite group.
```
###### Proof:
Take a basis for $G$, label it $\mathcal{G}  = \{g_{1},g_{2},\dots g_{n}\}$. Take a basis for $H$, label it $\mathcal{H} = \{ h_{1},\dots,h_{n} \}$.
Now there is an integer matrix $M$ such that $\mathcal{H} = M \mathcal{G}$.
Now we can take the vector space $G'$ over $\mathbb{Q}$ whose basis is $\mathcal{G}$.
In that vector space, $\mathcal{G}$ and $\mathcal{H}$ are both bases, hence $M$ is a base change matrix, hence is invertible.

Now $\det(M) M ^{-1}$ is an integer matrix.
This means $\det(M)g_{i} =$ some linear combination of $h_{j}'s$ with integer coefficients. This means $\det (M)G \subset H$.
This means $G /H$ is a finite group with size at most $|\det(M)| ^{n}$.

---
# References
