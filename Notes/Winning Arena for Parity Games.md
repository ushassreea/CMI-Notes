---
tags:
  - Note
  - Incomplete
---
202403201203

Tags : [[Games on Graphs]]
# Winning Arena for Parity Games
---
>[!tldr] Goal
>Given a parity game, we want to split the arena into 2 parts denoting the winning region for Rajnikant and Sreevani.
>

>[!fail] Naive strategy that fails
>The most obvious thing that does work would be the combination of two of these kinds of startegy
>- A)Keep visiting infinitely many times : Which is just the Buchi strategy
>- B)Eventually never visit : Which can be constructed in the following way.
>	- Take the bad set. 
>	- Find its attractor
>	- Consider the complement of the bad set. This is the largest trap outside the bad set.
>	- The attractor of the that.
>
>Now our winning set would be $A(n) \cup B (n-1) \cup A(n-2)  \cup \dots$
>Which would just be, we go to least import sets good set but not the bad sets that have a higher priority, or next good set with least priority and so on.
>
>This strategy fails because consider a situation where we consider visit a set $G$ again and again, and visit $B$ only finitely many times. It might be that if we want to visit $G$ infinitely many times, all paths would go though $B$, but at the same time, it might be possible to completely avoid $B$ if we don't care about visiting $G$ infinitely often. 
>These kinda of paths will not be eliminated and hence we will have a faulty strategy.
>

## Stealing the Rabin Game Strategy
The Parity can be very easily be converted to a Rabin game as follows.
For each $n$
- let $G_n$ be the set of all vertices that have the colour $2n$
- let $B_n$ be the set of all vertices that have a colour of odd parity of size less than $2n$

Now we just use the strategy described in [[Winning Arena for Rabin Games]].

--- 
## Proof that Parity Games are Determined
>[!tldr] Plan
>Consider the largest 1-paradise, and show that it's complement is a 0-paradise

Let $X^1_{i}$ be a $1$-paradise and consider all let $X^1 = \bigcup_{i\in I}$ be the union of all $1$-paradises which is the largest $1$-paradise.

But since $\text{attr}_0(X^1) \supseteq X^1$ and $\text{attr}_0(X^1)$ is a $1$-paradise, $X^1$ is its attractor, so the complement of $X^1$ is a $1$-trap.

We now restrict the game to the trap defined above. In that sub-game let $S_0$ be the set of points that have the colour $0$. 

Now we consider the part of the sub-game that is the complement of $\text{attr}_0(S_{0})$ which is a $0-$trap. Now in that sub-sub-game the number of colours used are significantly less, so by induction we can show that there is a partition sub-sub-game which are $0$ and $1$ paradises.

- In the sub-sub-game, the player $1$ paradise gives a winning strategy for player 1, which will word as long as player $0$ does not move the game to the set $X^1$ from which player $1$ also has a winning strategy, therefore the entire arena of the sub-sub-game is a $0$-paradise.
- The $0$-paradise gives a strategy for player $0$ that can be used as long as player $1$ does not go out of the sub-sub-game to the set $attr_0(S_{0})$. But if player 1 does that, player $0$ can then visit a node with value $0$ and after that either stay in the attractor or go back to the sub-sub-game. $(X^1)^c$ is a $0$-attractor.

![[Parity Games are determined.excalidraw|800]]

---
## Complexity of existence of a winning strategy in a finite-arena parity game.
>[!question] Problem
>Given a parity game $G$ and a vertex $v$ from the vertex set of $G$, can player $0$ force a victory.

>[!note] Complexity
>The problem is in [[NP (Complexity Class)|NP]] $\cap$ [[Co-NP (Complexity Class)|Co-NP]].
>This means that its highly unlikely that the problem is [[NP Complete]], but there is no known algorithm in [[P Complexity Class|P]] for the problem.

### NP Algorithm
>[!idea]
The Idea is to guess a strategy and to check if the strategy is winning in polynomial time.

We represent selecting a strategy by removing every outgoing edge from every $v\in V_0$ except for the one picked by the strategy, so our algorithm becomes as follows:
- We go to the description of each $v\in V_0$ and we remove all outgoing edges except for one that is picked that the strategy that was decided non-deterministically.
- In the reduced graph we now check that the strategy is correct by checking if there exists and odd-cycle in the same weakly-connected component as $v$.
	- This is done by doing a DFA from each vertex checking if there is a path from each vertex $v \in  V_1$ that comes back to $v$ and doesn't go over a vertex that has index less than that of $v$. 
	- This is used to detect a cycle with $v$ as the element with colour of least index. If we find one, then we halt the machine rejecting the input. otherwise we accept.

### Co-NP Algorithm.
Since the game is a zero-sum game without draws, if player $0$ cannot win, then player $1$ must be able to win. Hence, checking if player $0$ cannot win is the same as checking if player 1 can win. 

We use the same algorithm discussed in the previous section by modifying to so it checks if player 1 can win.

---
# References
[[Winning Arena for Büchi Games]]
[[Winning Arena for Reachability Games]]
[[sigma-paradise]]