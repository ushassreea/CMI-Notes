---
tags:
  - Note
---
202310241510

Tags : [[Theory of Computation]], [[Timed Automata]]

---
# Reachability in Lossy Channel Systems

>[!definition] Lossy Channel Systems 
>A **Lossy Channel System** is like a [[Channel Systems|Channel System]] but on each transition, the channel can lose some of its letters(from any part of the work) and become a subword.

>[!tldr] Plan
>We Encode the Channel runs as Timed Words, and we reduce the problem of *reachability* in **lossy channel systems** to *universality* of **one clock timed automata** which  is known to be *non-primitive recursive*.

## Encoding Channel runs as Timed Words
We use a one clock **Timed Automaton** to simulate a [[Channel Systems]] with one *Channel*.
Consider a run on a channel system, it consists of a sequence of configurations and transitions between them. We represent it in the following way.

I let the alphabet of the automata be $\Sigma\cup Q\cup(\Sigma^2\times \{?,!\})$ where $\Sigma$ is the alphabet of the *channel system* and $Q$ is its control. 
The the *timed word* representing a run of the system would have 
- $(q_n,a,x)$ at $t=0$ where $q_n$ is the last state in the run which was reached by accepting the letter $a$ and $x=!$ if $a$ was written and $x=?$ if $a$ was dropped.
- The contents $c_{n-1}$ of the tape are written letter by letter in order in time $(0,1)$
- At times $t=i$ where $i\in\mathbb N$ we have the $(q_{n-i},a,x)$ and in time $(i,i+1)$ we have $c_{n-i}$ written in a similar format.
- At time $t=n$ we have $q_0$ 
- We also enforce the condition that the corresponding letters in $c_i$ and $c_{i-1}$ are exactly $1$ time unit apart.

Now have a timed automata that accepts if either adjacent states and transitions are incompatible, or if there isn't a letter for channel configuration exactly 1 unit away.

Now we have reduced the problem of *Reachability* of channel systems to *universality* in a one clock timed automata. Which is known to be **Non-Primitive Recursive**.

---
# References
- [[Universality is Decidable for One-Clock Timed Automata]]
- [[Recursive and Recursively Eumberable Sets]]
- [[Primitive Recursion]]