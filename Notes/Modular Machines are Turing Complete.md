---
tags:
  - Note
  - Incomplete
---
202403260003

Tags : [[Undecidability in Algebra and Topology]]
# Modular Machines are Turing Complete
---
It is easy show that a Modular Machine can be simulated in a turing machine, we just keep the two number of the configuration in different tapes, description of a modular machine in a separate tape, and then all operations are simple recursive functions.

Showing the other direction is also fairly easy once the motivation behind building this machine becomes more obvious.

Modular Machines were built around $\mathbb{Z}^2$ to make them easier to work with in an algebraic context. They are also intentionally built to be Turing Complete where each step in the modular machine directly corresponds to a step of a Turing Machine.

>[!idea]
>The idea is to look at the step definition, and think of each of those numbers in a base-$m$ representation. In that case each of those number will become a string of those characters and in each step only the ends of the words will be altered. Visually orient the words in a manner that the ends that are altered point towards each other, and now even the $L$ and  $R$ in the definition correspond to moving the *Active Centre* around like the pointer in a turing machine.

We proceed with encoding a [[Turing Machine Configuration]] as our pair $(\alpha, \beta)$.

A Turing Machine Configuration looks like the following string 
$$
a_{n} a_{n-1}\dots a_{2}a_{1}\;qc\; b_{1}b_{2}\dots b_{m}
$$
where 
- $a_na_{n-1}\dots a_{2}a_{1}c b_{1}b_{2}\dots b_{m}$ is the content of the tape.
- The control of the machine is in state $q$ and t
- he pointer is pointing to the letter denoted by $c$.

---
## The Alphabet and the Modular Class
The operations in our Modular Machine are heavily dependent on the choice of the number $m$ (look at [[Modular Machines]] for definition). 

The steps of a modular machine give a hint that the numbers should be encoded in base-$m$. Hence given that we are allowed to use characters from the tape alphabet  and characters to represent set of states let 
$$
m = |\Gamma| + |Q|
$$
And we give the following encoding.

If $\Gamma = [\gamma_{0},\gamma_{1}\dots \gamma_{n-1}]$ we let the encoding of $\gamma_i$ be $i$. And if we label the states as $Q = [q_{0},q_{1}\dots q_{m-n-1]}$ we given $q_i$ the encoding $i+n$.

>[!note] Given an encoding, it is trivial to figure out if its the encoding of an alphabet or a state.
>If the encoding reads $i<n$ we can tell that its an alphabet, otherwise its a state.

Also now we write the number is base $m$, this gives a direct encoding from $\mathbb{N}$ to $\Gamma \cup G$.

---
## Constructing the Modular Machine
Now that we have a neat way have a way to generated word to represent Turing Machine Configuration, we would like to make the machine that acts of the configuration.

We already have a few ideas on how we want that to look and we can make a few inferences about the behaviour of our system.
- The least significant digits of $\alpha$ and $\beta$ correspond to the *active parts* of the Turing Machine, so keeping the character the head is pointing to, and the current state in those positions seems like a good idea. We will let the state be either the least significant digit of $\alpha$ or $\beta$ and we will let it interchange between those to position to make things convenient for us.
- All other positions, should correspond to the tape characters and hence have value $<n$.
- Notice that when moving left, we remove one letter from $\alpha$, and replace the last letter with 2 letters. The new least significant digit of $a$ is now a letter in our *active part*, which forces us to put the new state in the second one. This leaves us with one spot that will be taken by character written onto the tape.
	- Notice that this forces the number in which the encoding of the state will be in. (If we move left then $\beta$ otherwise $alpha$)
- Deriving $a$ and $b$ and picking a transition would directly correspond to reading the state and tape content to pick a transition.

Given all of that, we construct the machine in the following manner.
Given a transition $(q, a) \to (q', a', D)$ in the turing machine we make the following transitions in the Modular Machine 
- $(e(q), e(a),e(a')m+e(q'), D)$
- $(e(a), e(q),e(a')m+e(q'), D)$
Which intuitively reads as , we find transition corresponding to state $q$ and letter $a$, we move in the direction $D$ leaving being $a'$ and going to state $q'$. There are two transitions because the state information can belong to either of the words.

Also, since there are no out going edges from a final state in the turing machine, we will also get that out machine halts when and only when the turing machine halts.

---
## Encoding the Configuration
Given a configuration
$$
a_{n} a_{n-1}\dots a_{2}a_{1}\;qc\; b_{1}b_{2}\dots b_{m}
$$
We can construct 2 equivalent encodings for this
- $\alpha=\sum_{i} e(a_{i})\cdot m^i+e(q)$ and $\beta= \sum_{i} e(b_{j})\cdot m^j+e(c)$
- $\alpha=\sum_{i} e(a_{i})\cdot m^i+e(c)$ and $\beta= \sum_{i} e(b_{j})\cdot m^j+e(q)$

The two encodings correspond to the 2 possible positions of the state.

This Encoding makes sure that each step in the Modular Machine corresponds to eating a character from one side and putting 2 on the other, and that the current state and current header position of the turing machine are both correctly represented.

---

>[!tldr]
>- $m = |Q| + |\Gamma|$
>- Given a transition $(q, a) \to (q', a', D)$ we get the transitions
>	- $(e(q), e(a),e(a')m+e(q'), D)$
>	- $(e(a), e(q),e(a')m+e(q'), D)$
>- Given a start encoding $a_{n} a_{n-1}\dots a_{2}a_{1}\;qc\; b_{1}b_{2}\dots b_{m}$, we construct one of the two encodings
>- $\alpha=\sum_{i} e(a_{i})\cdot m^i+e(q)$ and $\beta= \sum_{i} e(b_{j})\cdot m^j+e(c)$
>- $\alpha=\sum_{i} e(a_{i})\cdot m^i+e(c)$ and $\beta= \sum_{i} e(b_{j})\cdot m^j+e(q)$ 


---
# References
[[Modular Machines]]
[[Turing Machines]]