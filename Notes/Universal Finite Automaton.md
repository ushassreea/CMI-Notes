---
tags:
  - Note
  - Incomplete
---
202404101204

Tags : [[Theory of Computation]]
# Universal Finite Automaton
---
A *Universal Finite Automata* is variant of the finite state automata a word is accepted if every single run of the word on the automata is accepted.

This is like the dual of a [[Non-Deterministic Finite State Automata]] where any one of possible runs of the word should be accepting for a word to be accepted.

Since each run can branch off to multiple runs, all of which should be accepting, it is convenient to consider a tree as a run instead of states.

## Expressive Power
From the following observations
- A [[Deterministic Finite State Automata|DFA]] is a *Universal Finite Automata*
- The subset construction can be used to construct a finite of the automata.
We can tell that for finite words *Universal Finite Automata* only accept regular languages.

>[!tip] Another slick way to prove the above fact
>To take the complement of a *Universal Finite Automata*, we simply make the good states the bad states and make the automata a [[Non-Deterministic Finite State Automata|NFA]].
>
>This shows that the complement of the language of a *Universal Finite Automata* are regular, hence the language of a *Universal Finite Automata* is regular.


>[!todo]
>Tree Diagram


---
# References
[[Alternating Finite Automaton]]