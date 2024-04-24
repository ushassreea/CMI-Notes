---
tags:
  - Note
  - Incomplete
aliases:
  - Kripke Structures
---
202309111109

Tags : [[Logic]]

---
# Kripke Models

A *Kripke Model* is a triple of the form:
$$
\mathcal C = \langle 
                  C
                , \le
                , \Vdash 
             \rangle
$$
Here:
- $C$ is a non-empty set, whose elements are called *states* or *possibilities worlds*.
- $\le$ is a partial order on $C$ which represent the "Timeline".
	- Sometimes a $R \subseteq C \times C$ successor relation is used instead of a partial order.
- $\Vdash$ is a binary relation between elements of $C$ and propositions which represents "The knowledge we know at that point in the timeline". AKA the labelling function.

---
## Example
### Mod 2
Program : x := x + y mod 2

### Concurrency
Copy Sreevani

---
# References
[[Linear Temporal Logic]]
[[Intuitionistic Logic]]
[[Some Applications of Kripke Structures]]