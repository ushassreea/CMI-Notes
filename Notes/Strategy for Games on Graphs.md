---
tags:
  - Note
  - Incomplete
---
202403061803

Tags : [[Games on Graphs]]
# Strategy for Games on Graphs
---
>[!hint] Notation
>Given a play $P$, a sub play after first $m$ moves to the first $n$ moves is defined as $P[m\dots n]$ (indexing starts at 0)
>We also define $P[m]$ to be the vertex the game is in after the exactly $m$ moves. Also $P[m] = P[m\dots m]$

A strategy is essentially a picking function. It chooses the next vertex for the game for a player.

Given that the existence of vertices with no out-neighbours is possible, we need to define strategy of a player as a sensible partial function from a sequence of states reaching their state to their next choice. This notion is formalised below.

>[!definition] Strategy
>A *strategy* of a player $\sigma$ is a partial function $f$ such that
>$$
>f: V^*\ V_{\sigma} \to V
>$$
>and $f$ is defined on $V^*\ V_\sigma$ if there exist out-neighbour of $V_\sigma$.

We say a run $R$ follows a strategy $f$ for player $\sigma$ if
$$
\forall i\in \mathbb{N},\quad R[i]\in V_{\sigma}\to R[i+1]=f(R[0\dots i]) 
$$

>[!Definition] Winning Strategy and Decidable Games
>A strategy $f$ for player $\sigma$ is called a *winning strategy* if all run following the strategy are winning for $\sigma$.
>
>A game is called *Decidable* if given each position. There is exactly one winning strategy 

---
# References
[[Winning Condition for Games on Graphs]]
[[Gameplay for Games on Graphs]]