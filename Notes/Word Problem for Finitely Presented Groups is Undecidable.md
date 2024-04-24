---
tags:
  - Example
---

202404021206

tags : [[Undecidability in Algebra and Topology]]

# Word Problem for Finitely Presented Groups is Undecidable
---
>[!definition] Solvable Word Problem
>Let $G = \langle S\; |\; R \rangle$  be a finitely presented group and $W$ be the set of all words in $S$. We say $G$ has a *solvable word problem* if the set $\{ w\in W\;|\; w =_{G} 1\}$ is decidable.

>[!History]
>This result is usually termed Novikov-Boone Theorem as it was proven independently by Pyotr S. Novikov and William W. Boone in 1955 and 1958 respectively and John L. Britton gave a simple proof in 1963.
>The following proof is by Ståal Aanderaa and Daniel E. Cohen in 1980

>[!theorem]
>There is a finitely presented group for which the word problem is *unsolvable*

---
## Proof Sketch
Let $\mathcal M$ be a [[Modular Machines|modular machine]] for which the halting set $H_{\mathcal M} = \{ (\alpha, \beta) | (\alpha,\beta) \xrightarrow{\mathcal M} (0,0) \}$ is undecidable.

>[!idea] Idea
The rough sketch of the proof will be that if given an $\mathcal M$, we will construct a group $(G'_{\mathcal M})'$ fir which the word problem will be solvable if and only if halting set $H_\mathcal M$ will be decidable. Since $H_\mathcal M$ is undecidable, word problem for $(G_\mathcal M')'$ is unsolvable.

- We start by defining a group $G$ to encoding configuration of modular machines.
- Then we define $G'_{\mathcal M}$ for encode the definition of the modular machine $\mathcal M$.
- Then we construct the group $(G'_\mathcal M)'$ to give group elements in $G'_\mathcal M$ corresponding to halting configurations special properties in a way that some words built using those elements evalutate to identity if and only if the machine halts on the corresponding configuration.

The detailed proof is discussed below:
[[Proof for the Undecidability of the Word Problem]]

---
# Related
[[Modular Machines]]
[[Proof for the Undecidability of the Word Problem]]