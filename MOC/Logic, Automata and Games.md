---
tags:
  - MOC
sticker: lucide//map-pin
---
# Logic, Automata and Games
---
>[!faq] What is this course about?
>The first part of the course is about automata over infinte words and their relation to logics.
>
>Logics give us a very expressive language to write statements to describe a system or specifications that a system should meet, this is why they are used in software verification and design.
>
>Automata are fairly low level machines, that are usually used to build algorithms and to evolution of systems. This is why they are also used in software verification. 
>
>The strong relation between Automata and Logic also gives us Automata Theoretic Approaches to deal with problems regarding logics.
>
>The second part of the course deals with games whose winning conditions are specified by logical formulas. These are tools that let us model multiple behaviours(strategies) of the environment(opponent) on the system(us). In this part we will study how to setup such games given logical formulas and use automata to model them.
---
## Course Plan
1. Büchi Automata and Omega Regular Languages
2. Monadic Second Order Logic and their relations with Büchi Automata
3. Linear Temporal Logic and its relation with Büchi Automata
4. Games and Why
5. Characterisation and strategies for different types of games

--- 
## Notes
### Part 1 : Logic and Automata
- [[omega-Automata]]
	- [[Büchi Automata]]
		- [[Another way to Complement a Büchi Autromata]]
		- [[Deterministic Rabin Automata accept omega-regular languages]]
		- [[Last Appearance Record]]
	- [[Language of Infinite words]]
	- [[Omega-Regular Languages]]
	- [[Closure Properties of Büchi Automata and Omega-regular languages]]
		- [[Lemma 1 for Complementation of omega-Regular Languages]]
		- [[Lemma 2 for Complementation of omega-Regular Languages]]
		- [[Lemma 3 for Complementation of omega-Regular Languages]]
		- [[Another way to Complement a Büchi Autromata]]
	- [[Set of Languages accepted by Büchi Automata are exactly Omega-Regular]]
	- [[hat V- Deterministic Büchi Automata]]
- [[Monadic Second Order Logic]]
	- [[Büchi Automata for Monadic Second Order Logic]]
	- [[Strings in Logic]]
- [[Linear Temporal Logic]]
	- [[Semantics for LTL]]
	- [[Büchi Automata for Linear Temporal Logic]]
		- [[Closure and Atoms for Büchi construction of LTL formulas]]

### Part 2 : Games
- [[Games on Graphs]] (MOC)
	- Basics
		- [[Arenas for Games on Graphs]]
		- [[Gameplay for Games on Graphs]]
		- [[Winning Condition for Games on Graphs]]
	- [[Strategy for Games on Graphs]]
		- [[Winning Arena for Reachability Games]]
			- [[Winning Strategy for Reachability Games]]
		- [[Winning Arena for Büchi Games]]
			- [[Winning Strategy for Büchi Games]]
		- [[Winning Arena for Parity Games]]
		- [[Winning Arena for Rabin Games]]
			- [[Winning Arena for Rabin Games - Fail]]
	- [[Sub-Games]]
	- [[Properties of the Attractor function and Traps]]
	- [[sigma-paradise]]
	- [[Alternating Finite Automaton]]

--- 
## MOCs
- [[Games on Graphs]]

---
# References
- [Technical University of Munich notes on omega-Automata](https://teaching.model.in.tum.de/2021ws/afl/slides2021/11-Omega-Automata.pdf)
- Parameterized Complexity Theory - Jörg Flum and Martin Grohe
- [Madhavan's Notes on Büchi Automata and LTL](https://moodle.cmi.ac.in/pluginfile.php/32404/mod_resource/content/0/isical97.pdf)