---
tags:
  - Note
  - Incomplete
---
202403241003

Tags : [[Games on Graphs]]
# Winning Strategy for Büchi Games
---
## Rajnikant
>[!Theorem] Lemma
>Rajnikant has a winning strategy from $\text{attr}_{0}(A, Z(n))$ if $Z(n) = Z(n+1)$

- Case 1 : $v\in Z(n)$
	- then $v\in Z(n+1)$, by the definition of $Z$ we have $v\in \text{pre(attr}_{0}(A, Z_{n}))$, then we can continue for case 2
- Case 2 : $v \notin Z(n)$
	- In this case we can always move to some node in $Z_n$ as $v\in \text{attr}_{0}(A, Z(n))$

---
## Sreevani
>[!theorem] Lemma
>Sreevani has a winning strategy from $V\setminus \text{attr}_{0}(A, Z(n))$

We notice that $A_S$ is the complement of an attractor set. So Sreevani will use the trapping strategy to keep the game away from $A_R$ using the strategy discussed in [[Winning Arena for Reachability Games]], until the play Visits a vertex in $X$.

For this position we have $A_S = V \setminus X(n)$. Let $i$ be the largest index such that $v\in X(i)$ but $v\notin X(i+1)$, so Sreevani can keep the game out of $\text{attr}_{0}(Z(i+1))$. 

Here Sreevani uses trapping strategy to keep the game out of $attr_0(Z(i+1))$ till the game reaches a point $v$ in $G$. We have that $v\notin Y(i)$ so after a move, we can go outside $X_i$, hence we go outside $\text{attr}_0(Z(i))$ and Sreevani uses trapping strategy again.

Hence the game will remain out of $X(j)$ forall $j>i$. Therefor the next $v\in G$ that is visited will be in $X(k)$ where $k$ is less than $i$, but the same idea is used. This process cannot go on indefinitely hence eventually the game will remain out of $X_1$ which contains $G$.

At some point we will reach $X(0)\setminus X(1)$ which is the set of points from where Sreevani can force the game to only those vertices that are not good states, or are dead ends for Rajnikant. Hence Sreevani has a winning strategy.

Modifying the algorithm in the following manner makes it easier to see that Sreevani might have a winning strategy.

```
Let Z(0) = V
until Z(i) stabilizes:
  X(i) = Attr_0(A, Z(i))
  Y(i) = pre(X(i))
  Z(i+1) = Y(i) /\ Z(i)
end until at n
return Attr_0(A, Z(n))
```

---
# References
[[Winning Arena for Büchi Games]]
[[Winning Arena for Reachability Games]]
[[Winning Strategy for Reachability Games]]