---
tags:
  - Note
  - Incomplete
---
202403181103

Tags : [[Type Theory]]
# Dependent Types
---
>[!tip] Programmer's POV
>A *Dependent Type* is one that depends on an object value. For instance the type `[type; nat]` is the like type of slices in rust, where the first argument is the type of elements of the size and the second argument is a natural number denoting the size of the slice. So here the expression `\x -> [int; x]` is like a type constructor where it takes in an integer and returns a type, hence its has the kind $\text{int} \to \star$.




---
# References
