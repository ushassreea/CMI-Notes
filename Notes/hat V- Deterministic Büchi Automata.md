---
tags:
  - Note
---
202401171401

Tags : [[Automata Theory]], [[Logic]]
# $\hat V$ : Deterministic
---
>[!attention] Notation Abuse
>I will be using characters like $V$ for both a language and an automata for the langauge. 

Given a regular language $V\subseteq \Sigma^*$, consider the following language
$$
\hat{V} = \{ \alpha| \text{ infinitely many prefixes of $\alpha$ belong to $V$} \}
$$
Is the above language $\omega-$regular. If yes, how to find a *Büchi Automata* that will accept the language.

Then answer is yes, and it is fairly easy.... given that the above automata is a *DFA*. If that is the case, then we can just take the *DFA* and replace the final states with good states and turn it into a *Büchi Automata*.

![[Hat-V-Run.excalidraw]]

>[!idea] Why it works
>In a *DFA*, Run of a prefix is the same as the prefix of a run, as it only depends on the characters read.
>So if infinitely many prefixes were accepted by the automata, each of these prefixes end on a good state. So the good states are visited infinitely many times.

If the above automata is not a *DFA*. Then the same construction does not work.

Consider a candidate $V=aa^*a$ with the following *NFA*.

![[aa*a-NFA.excalidraw]]

The language that $\hat V=a^\omega$ but the corresponding *Büchi Automata* if we get it directly for the *NFA* doesn't accept any word. 

Although we have proved that for any regular language, the above procedure can be done using a *DFA*, any $\hat V$ can be accepted by a *Deterministic Büchi Automata*.

## Informal Introduction to Rabin Automata
From the closure properties of regular languages, we know that given two $\omega$-regular languages $U$ and $V$. We know that $U\cdot \hat V$ is $\omega-$regular.

A simple way to construct a *Büchi Automata* that accepts this would be to take the *DFA* for $U$ and the *Büchi Automata* for $\hat V$, and make $\epsilon-$transitions from final states if $U$ to the start state of $\hat V$.

![[U-Hat-V-Buchi.excalidraw]]

This happens to be a non-deterministic. At the places where the two automata are connected by the $\epsilon-$transitions. And there is no easy way to get rid of it because whenever we reach a final state of $U$, there is no way to be sure if it is time to switch to the other automata, or stay in $U$ for some more letter.


---
# References
[[Deterministic Rabin Automata accept omega-regular languages]]
