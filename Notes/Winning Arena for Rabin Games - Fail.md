---
tags:
  - Note
  - Incomplete
---
202403292303

Tags : [[Games on Graphs]]
# Winning Arena for Rabin Games - Fail
---
>[!tldr] Goal
>Given a parity game, we want to split the arena into 2 parts denoting the winning region for Rajnikant and Sreevani.
>

>[!error] This does not word

![[Winning Arena for Rabin Games#Simple Case - 1 pair of sets]]
## General Case
Now that we have a method to show that a strategy exists in teh case where there is exactly one pair of good and bad states we can generalise to the case where we are given the set $\{(G_i, B_i)\}_{i\in I}$.

Corresponding to each $(G_i, B_i)$ we give a strategy $\sigma_i$ which is obtained by doing the process in the previous section assuming other pairs do not exist.

We first give a well ordering to the set $I$.

Now given any vertex $v\in V$ if the strategies $\sigma_j$ are defined for $j\in J\subseteq I$ then we pick $\alpha = \min J$ and let $\sigma(v) = \sigma_\alpha(v)$.

This gives us a strategy in the general scenario.

This means that, if we are a vertex where $\sigma(v) = \sigma_{\alpha}(v)$ the strategy will force the game to go to a vertex $\sigma(v) = \sigma_{\alpha'}(v)$ where $\alpha' \leq \alpha$.

But since there are no infinite descending chains in well orders we will reach $\alpha_{\min}$ in finitely many steps from where $\sigma(v) = \sigma(\alpha_\min)$ and we visit $G_{\alpha_\min}$ infinitely many times without visiting $B_{\alpha_\min}$ infinitely many times.

>[!error] Why does this not work?
>The idea works perfectly for the basic scenario where there is just 1 pair of good and bad set of states.
>
>This fails when we generalise because the idea is to solve each pair independently getting states that are definitely good for player 0 and then take the union, which does work, the player 0 paradise that we end with is definitely winning for player 0, but the complement is not necessarily good for player 0. The player 0 startegy gets spoiled because a paradise may be shrinked for a points that are later proven to be good for player 1. 
>
>I have not been able to resolve that issue, the set is simply not a sigma-paradise for player 1. 

---
# References
[[Winning Arena for Parity Games]]
[[Winning Arena for Rabin Games]]
[[Winning Arena for Büchi Games]]
[[Winning Arena for Reachability Games]]
[[sigma-paradise]]