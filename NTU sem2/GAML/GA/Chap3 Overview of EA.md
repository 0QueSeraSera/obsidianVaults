# General Procedure
![[Pasted image 20230421102343.png]]
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
![[Pasted image 20230421102746.png]]
- Sets of Individuals (genotypes)
- Basic unit of evolution
	- *Selection* operates on population
	- _Variation_ operates on individuals
## 4. Selection Schemes
including _parent_ selection and _next generation_ selection
![[Pasted image 20230217111821.png]]
### Example: roulette wheel selection
in principle
![[Pasted image 20230217111931.png]]
### Survivor Selection
Decide _who can go to the next generation_ from the current generation's parents and offspring
![[Pasted image 20230217112149.png]]



## 5. Variation Operators
mainly mutation and recombination
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
The mapping here, each bit means the row id of queens
![[Pasted image 20230217113135.png]]
## 2. Evaluation
![[Pasted image 20230217113234.png]]
## 3. Variation
### Mutation
![[Pasted image 20230421105930.png]]
### Recombination
![[Pasted image 20230421110005.png]]

## 4. Selection
each time, _randomly_ choose 5 parents and select 2.
![[Pasted image 20230421110215.png]]

## Summary and terminology
![[Pasted image 20230421110247.png]]

# SGA Example: f(x) = x^2
![[Pasted image 20230421110949.png]]
## 1. Encoding
One integer variable from 0 to 31. Use _5-bit binary_
![[Pasted image 20230421110626.png]]
## 2. Init population
Randomly init
## 3. Compute fitness
## 4. Reproduction
Use Roulette Wheel here
## 5. Crossover
![[Pasted image 20230421111127.png]]
![[Pasted image 20230421111340.png]]

## 6. Mutation
