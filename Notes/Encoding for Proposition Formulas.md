---
tags:
  - Note
---
202403072303

Tags : [[Logic]]
# Encoding for Proposition Formulas
---
Now that we have a [[Succinct Encoding of Natural Numbers Using Strings]]. We can use that give an efficient encoding for Propositional formulas in *CNF* form. We will give a sequence of encodings of propositional formulas and assignments to variables of these formulas, so that we need shorter and shorter first order formulas that claim that the given assignment satisfies the given formula.

The idea is to use encodings for natural numbers to encode propositional variables by their index. Then we can use very formulas to check if two subwords of a codeword that represent the variables actually represent the same.

We build our alphabet by adding first considering the following variables

```
+, -, <lit>, </lit>, <clause>, </clause>, <cnf>, </cnf>
```

## Encoding Formulas
### Literals
We define literals in the following way 
```
mu_h(lambda) | lambda == X_i  = <lit> mu_h(i)+ <\lit>
mu_h(lambda) | lambda == -X_i = <lit> mu_h(i)- <\lit>
```

### Clause
A clause in a *CNF* formula is a sequence of disjunctions joined together by conjunctions.

We define clauses as follows
```
mu_h(delta)=<clause>mu_h(lambda_1)...mu_h(lambda_n)</clause>
```

### CNF
A *CNF* formula is a conjunction of clauses and can be defined as below
```
mu_h(gamma)=<cnf>mu_h(delta_1)...mu_h(delta_m)</cnf>
```
## Encoding Assignments
An assignment is a function from the of propositional variables to $\{\top,\bot \}$.
Here we add 
```
<val>, </val>, <asn>, </asn>, true, false
```
For an assignment $\alpha$ we can give the following encoding to it.
```
mu_h(alpha) = <asn>
                   <val>mu_h(0) alpha(X_0)</val>
                   .
                   .
                   .
                   <val>mu_h(n-1) alpha(X_n-1)</val>
              </asn>
```

---
## Size of the encodings
Using a similar idea for the proof of size of encoding of natural numbers discussed [[Succinct Encoding of Natural Numbers Using Strings#Size of the Encoding|here]], we get the following Theorem

>[!theorem]
>Let $H\in \mathbb{N}$ and $(\gamma, \alpha)\in \text{CNF}(n)\times A(n)$ then $|\mu_h(\gamma, \alpha)| = O(h\cdot(\lg n)^2 \cdot(\|\gamma\|+n))$ and there is an algorithm that computes it time linear to the size of the output.
>  

We discuss the part about short first order formula verifying if a given assignment satisfies the formula [[FO for Verifying CNF Encoding|here]]

---
# References
[[Succinct Encoding of Natural Numbers Using Strings]]
[[Encoding of Tuples]]