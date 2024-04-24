---
tags:
  - Note
---
202311031511

Tags : [[Theory of Computation]]
# Alternating Finite Automaton
---
>[!important] Motivation
> Some of the basic operations that [[regular languages]] are closed under are really simple to perform on a *Deterministic Finite Automaton*, but not as easy as a *Non-Deterministic Finite Automaton*. Specifically complementation.
> *NFAs* cannot be trivially complemented because a word can have multiple runs that may or may not reach a final state. Dealing with all of them together makes the process easier.
> The problem is created because there is a tool to deal with disjunction of runs, namely non-determinism. But there isn't a tool to deal with conjunctions.
> Alternating Finite Automata offer us that tool.
> 
> It can also be thought of as a combination of a [[Non-Deterministic Finite State Automata|NFA]] and a [[Universal Finite Automaton]]

The idea is to give transitions that allow a letter to go to multiple states, but with an *and* condition. That is, all runs that diverge at this set of transitions much reach accepting states.

An *Alternative Finite Automaton* is an *NFA* where the following changes are made to transitions.
$$
\delta: Q\times \Sigma\to 2^{2^Q}
$$
Intuitively, the transitions in the above set represent disjunctions of transitions that, from a state after accepting a letter, goes to a set of states and all runs from that state should go to final states.

## Expressive Power
*Alternating Finite Automata* can accept regular langauges.
This is because  there is a direct construction of an *AFA* to an *NFA*, that is the subset construction, where the final states of the *NFA* $2^F$ if $F$ is the set of final states in the *AFA*. 

---
## Closure Properties
*Alternating Finite Automata* are closed under
- Union and Intersection (use the new transition to directly get a new construction)
- Complementation (Replace all the accepting and non accepting states, and switch all $\land$ and $\lor$ in the transition)

---
# References
[Wiki](https://en.wikipedia.org/wiki/Alternating_finite_automaton?useskin=vector)
[[Alternating Timed Automata]]
[[Universal Finite Automaton]]