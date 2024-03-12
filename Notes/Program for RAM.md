---
tags:
  - Note
  - Incomplete
---
202403061903

Tags : [[Theory of Computation]]
# Program for RAM
---
A Program for a *RAM* is a labelled set of instructions, similar to an assembly language with the following instruction
>[!attention] Notation
>Let $c(i)$ refer to the value in the $i^{th}$ register and let $v(i)$ refer to the value given to the program when it reads $i$, we define it as follows.
>- $v(i) = c(i)$
>- $v(=i) = i$
>- $v(*i) = c(c(i))$ 

- Instructions that take in an operand
	- $\text{LOAD}$ 
		- $\text{LOAD }a$ : $v(a) \to c(0)$
	- $\text{STORE}$
		- $\text{STORE }a : c(0) \to c(a)$
		- $\text{STORE } *\!a : c(0) \to c(c(a))$
	- $\text{ADD}$
		- $\text{ADD }a : v(a)+c(0) \to c(0)$
	- $\text{SUB}$
		- $\text{SUB }a : v(a)-c(0) \to c(0)$
	- $\text{MUL}$ - Not in the paper
		- $\text{MUL }a : v(a)*c(0) \to c(0)$
	- $\text{DIV}$ - Not in the paper
		- $\text{DIV }a : \lfloor v(a) / c(0)\rfloor \to c(0)$
	- $\text{READ}$
		- $\text{READ }a :$ current input symbol $\to c(a)$
		- $\text{READ }*a :$ current input symbol $\to c(c(a))$
		- In both cases the input pointer moves one step right.
	- $\text{WRITE}$
		- $\text{WRITE }a : v(a)$ is written onto the current cell of output tape and the pointer is moved one step to the right. 
- Instructions that take in a Label
	- $\text{JUMP}$
		- $\text{JUMP }b :$ location counter is set to instruction labelled $b$
	- $\text{JGTZ}$
		- $\text{JGTZ } b :$ Location counter is set to instruction labelled $b$ if $v(0)>0$, otherwise it is set to the next instruction
	- $\text{JZERO}$
		- $\text{JZERO }b:$ Location counter is set to instruction labelled $b$ if $v(0)=0$, otherwise it is set to the next instruction
- Miscellaneous
	- $\text{HALT}:$ execution ceases


---
# References
