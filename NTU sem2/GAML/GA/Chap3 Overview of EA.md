# General Procedure
![[Pasted image 20230217110611.png]]
**Random** Initialization
Evaluate candidates
Repeat:
	**Parent** Selection
	**Recombination** of Parents
	Offspring **Mutation**
	Eval Offspring
	**Next Generation** Selection
![[Pasted image 20230217110928.png]]

# Components
## 1. Representation
![[Pasted image 20230217111047.png]]
Example:
![[Pasted image 20230217111244.png]]

## 2. Evaluation (Fitness) Function
![[Pasted image 20230217111355.png]]
## 3. Population
- Sets of Individuals (genotypes)
- Basic unit of evolution
	- *Selection* operates on population
	- _Variation_ operates on individuals
## 4. Selection Schemes
![[Pasted image 20230217111821.png]]
### Example: roulette wheel selection
![[Pasted image 20230217111931.png]]
### Survivor Selection
Decide _who can go to the next generation_ from the current generation's parents and offsprings
![[Pasted image 20230217112149.png]]



## 5. Variation Operators
![[Pasted image 20230217112707.png]]
### Mutation
![[Pasted image 20230217112827.png]]
### Recombination
![[Pasted image 20230217112931.png]]
## 6. Initialization / Termination
![[Pasted image 20230217113016.png]]



# Example: 8 queens
## 1. Representation
- phenotype and genotype
![[Pasted image 20230217113135.png]]
## 2. Evaluation
![[Pasted image 20230217113234.png]]

... similar stuffs
