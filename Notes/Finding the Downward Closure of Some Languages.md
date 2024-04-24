---
tags:
  - Note
  - Incomplete
---
202403150903

Tags : [[Infinite State Verification]]
# Finding the Downward Closure
---
>[!definition] Property
>$D \downarrow$ is the downward closure of $D$ then $\overline{D \downarrow}$, then there are finitely many minimal elements in $\overline{D \downarrow}$. Let this set be $\{ x_{1}\dots x_{n} \}$
>

We let $Y_i = \{ y\; |\; x_{i} \not\prec y \}$ which is the same as $\overline{x_{1}\uparrow}$, so we can define the downward closure to be the following
$$
D\downarrow = \bigcap_{i=1}^n Y_{i}
$$

Here for each $Y_i$ we construct a [[Simple Regular Expressions]] which will be used to effectively compute the downward closure of the entire language.

If $x_{i} = a_{1}\dots a_{n}$ and $\Sigma_i = \Sigma \setminus \{ a_i \}$ so we have 
$$
Y_{i} = \Sigma_{1}^*(a_{1}+\epsilon)\Sigma_{2}^*(a_{2}+\epsilon)\dots(a_{n-1}+\epsilon)\Sigma_{n}^*
$$


---
# References
[[Simple Regular Expressions]]