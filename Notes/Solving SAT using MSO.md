---
tags:
  - Note
---
202403111703

Tags : [[Logic]]
# Solving SAT using Monadic Second Order Logic
---
Given that we can now [[Encoding for Proposition Formulas|encode CNF formulas]] in words, we will now try to give a formula that states that given *CNF* formula, there exists an assignment for it that satisfies it.

For this, we will be taking a subset of propositions and declaring them to be *True*. Quantification over sets means [[Monadic Second Order Logic|MSOL]] is a powerful enough logic for the task.

>[!tip] The Formula
>We have already figured out a formula $\varphi_{h, l}(x)$ as defined in [[FO for Verifying CNF Encoding]].
>This formula checks if a given assignment of variables satisfies the proposition. We want to quantify of all assignments, so we modify it to get the following
>$$
>\tilde{\varphi}_{h, l} =
>\exists X(\forall x(x \in X \to P_{V_{1}}) \land \varphi'_{h, l})
>$$
>Where $\varphi'_{h, l}$ is the formula obtained by replacing $P_{\text {true}}$ with $X$ in $\varphi_{h, l}$.
>>[!idea] How does this quantify over all assignments
>>The implication implies used in the formula enforces $X$ to only care about points that are in the default assignment (all true). This essential means $X$ becomes a subset of the assignment, given us a subset of variables that will have value true while the variables outside $X$ will have value false.
>
>The entire point of all this is the following
>$$
>\mu_{h+1}(\gamma,\star) \models \tilde{\varphi}_{h+1, l} \iff \gamma \text{ is satisfiable.}
>$$



---
# References
