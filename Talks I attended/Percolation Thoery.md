# ANIRUDDHAN"S TALKKKMKKKKK

- ## Percolation Theory
	- Consider the lattice $\mathbb{Z}^2$ that gives you a square grid and each edge is open w probability is $p$
	- Let $\theta(p)$ is the probability that the connected component that contains the origin is infinite.
		- Intuitively this should be an increasing function.
	- $p_{c}:= \text{inf}\{ p>0 | \theta_{p}>0 \}=\frac{1}{2}$ 
	- Idea is that we uniformaly assign a value to each edge, and close edge if value is more that $p$. Coupling argument.
	- Extension to $\mathbb{Z}^d$, all corresponding $p_c^{(d)}$ are strictly 
	- theta grows lineary from pc and drops exponentially as it goes below it. so there is some notion of a sharp phase transition for a lattice of a finite size.
	- What if origin is not any special vertex, then what is the probability of there existing an infinite cluster in the lattice.
		- If $p>p_c$ then prob of inf cluster is $1$.
		- If $p < p_c$ then prob of inf cluster if $0$.
	- Now we look at the dual of a graph.