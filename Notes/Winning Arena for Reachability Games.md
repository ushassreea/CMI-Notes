---
tags:
  - Note
---
202403201203

Tags : [[Games on Graphs]]
# Winning Strategy for Reachability Games
---
>[!tldr] Goal
>Rajnikant wants to reach a particular node $x$ in the graph. We want to partition the arena into the winning region for Rajnikant($\mathcal A_R$) and Sreevani($\mathcal A_{S}$).

To do the following, we will start with an empty $\mathcal A_R$ and will incrementally add elements to it till we are done.

We define the following function to increment the set.
```
pre(S : Set) -> Set {
    S' = []
    forall (v in VR | v is adjacent to S)
        S'.add(v)
    forall (v in VS | v is only adjacent to S)
        S'.add(v)
    return S'
}
```

^134833

>[!idea]
>This reads as, if the vertex belongs to Rajnikant and is next to his arena then it belongs to the arena. And if the vertex belongs to Sreevani and is forced to go into Rajnikant region then it belongs to Rajnikant region.

The use the above idea in the next algorithm.

```
let A_R(0) = [x]
until A_R(i) stabilizes:
   A_R(i+1) = pre(A_R(i)) \/ A_R(i)
end until at n
return A_r(n)
```

^693834

If $\mathcal A_R(i)$ stabilised for $i=k$ we let $\mathcal A_R = A_R(k)$ and $\mathcal A_S = V \setminus A_R$.

---
## Strategies
### Rajnikant
For player Rajnikant, if the vertex belongs to $A_R$, it belongs to some $\mathcal A_{R}(i)$ and not in $\mathcal A_{R}(i-1)$, but it has an edge to it.
So Rajnikant chooses to go to a vertex in $A_R(i-1)$. By construction, Sreevani is forced to go to $\mathcal A_R(i-2)$. This process must terminate at $\mathcal A_R(0)$.

### Sreevani
If some vertex belongs to $\mathcal A_S$ then it does not belong to any $\mathcal A_R(i)$. 
This means it does not belong to `pre(A_R(i))`. Hence, its Rajnikant's turn, he cannot go to any $\mathcal A_R(i)$ and if its Sreevani's turn, she can choose to stay away from $\mathcal A_R(i)$. Thus the game never goes to the target node $x$.

>[!attention] Proof is omitted as its kinda trivial
>

---
# References
[[Strategy for Games on Graphs]]
[[Winning Arena for Büchi Games]]
[[Winning Strategy for Büchi Games]]
[[Winning Strategy for Reachability Games]]