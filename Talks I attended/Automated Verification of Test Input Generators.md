---
tags:
  - Note
  - Incomplete
---
202403191603

Tags : [[Logic]], [[Type Theory]]
# Automated Verification of Test Input Generators
---
- **Incorrectness Logic** - How do you prove that a program is wrong
- Verification
	- Good Assurance + Good effort = functional verification
	- Bad assurance + low effort = random testing
	- Good middle ground = property based testing.
- Input Generator
	- Soundness - The generator must produce inputs that satisfy the precodition (if not, we check wrong things)
	- Fairness - The generator must not have a bias towards a subset of inputs (if not we migth miss out on bugs from inputs that generator does not like)
	- Completeness - Given enough time, can generate all inputs. (Valid portions of inputs space might not be explored.)
- Program Logic
	- Hoare Logic
		- $\{ P \} \quad e\quad \{ Q \}$ iff $\text{post}(e)P \subseteq Q$
		- Overapproximation safety verification
		- Liquid Types / refinement typing
	- Incorrectness Logic
		- $[P ]\quad e \quad [Q]$ iff $\text{post}(e)P \supseteq Q$
		- Underapproximation Coverage Testing
		- Coverage Types
	


>[!quote] Some IITM person
>Input ==PERCENTAGE== 2

---
# References
