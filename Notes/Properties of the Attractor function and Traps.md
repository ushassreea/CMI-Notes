---
tags:
  - Example
---

202403271204

tags : [[Games on Graphs]]

#  Lemma about Attractor function
---
>[!Theorem] Lemma
>1. The set $V\setminus \text{attr}_{0}(G, X)$ is a $\sigma$-trap in $G$
>2. If $X$ is a $\sigma$-trap in $G$. then so is $\text{atrr}_{0}(G, X)$
>3. $X$ is a $\sigma$-trap in $G$ iff $\text{attr}_{0}(G,V\setminus X)=V\setminus X$.
>4. If $\text{attr}_{0}(G, X) = V\setminus U$ where $U$ is the greatest $\sigma$-trap contained in $V\setminus X$

## Proof
### 1
![[Winning Strategy for Reachability Games#Sreevani]]

### 2
The $\hat{X}= \text{attr}_{\bar{\sigma}}(G, X)$ is a superset of $X$.
- If the game starts in $v\in X$, $\bar{\sigma}$ uses the trapping strategy
- If the games starts in $v \in \hat{X} \setminus X$ then $\bar{\sigma}$ uses the reachability strategy to $X$, then uses the trapping strategy.

### 3
- Left to Right
	- If $X$ is a $\sigma$-trap, then the $\text{attr}_{\sigma}(G, V \setminus X)$ cannot contain any point outside $V \setminus X$ as that would be in $X$ and $\bar{\sigma}$ can trap the game in that set.
- Right to Left
	- If $\text{attr}_{\sigma}(G, V \setminus X)=V \setminus X$, then for any vertex $v\in X$ if $\sigma$ can force the play to go to $V\setminus
	- If $\text{attr}_{\sigma}(G, V \setminus X)=V \setminus X$, then for any vertex $v\in X$ if $\sigma$ can force the play to go to $V\setminus X$ then $v$ would be in the attractor which is a contradiction. Hence any point in $X$ can be forced to remain inside $X$ by $\bar{\sigma}$, that would be the trapping strategy.
	- Can be constructed by showing $v\notin \text{Pre}(V \setminus X)$

### 4
There always exist a largest attractor in any restriction of the game as union of arbitrarily many attractors is an attractor.

Given any set $X$, any trap $\sigma$-trap $W\in V \setminus X$ does not intersect with $\hat{X}=\text{attr}_{0}(G, X)$. And from [[Properties of the Attractor function and Traps#1|Point 1]] we know that $U = V \setminus \hat{X}$ is a $\sigma$-trap. 

Also we know that any point in $\hat{X}$ is not in a $\sigma$-trap what does not intersect with $X$.

Hence $U$ is the largest such attractor.

---
# Related
[[Sub-Games]]