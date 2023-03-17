[[Chap4 Representation Mutation & Recombination]]
****
# Real value or Floating point
Note the form of genes: **vector of k real valued elements**
![[Pasted image 20230219230054.png]]
## Mutation
Change the entire value, instead of bits
categorized with probability distribution
![[Pasted image 20230219230441.png]]
#### Uniform Mutation
![[Pasted image 20230219230604.png]]
#### Nonuniform Matation
- small change 
- drawn from Gaussian Distribution
![[Pasted image 20230219230754.png]]
The mean is 0, Std is called **_mutation step size_**
![[Pasted image 20230219230940.png]]
#### Self-adaptive mutation
Mutation step size evolves along the way
![[Pasted image 20230219232013.png]]
To achieve this 'coevolve', `sigma` must be modified first, before gene mutation

![[Pasted image 20230219232434.png]]

#### Uncorrelated Mutation with 1 sigma
![[Pasted image 20230219232552.png]]
![[Pasted image 20230219232706.png]]
these 2 formulas specify the mutation mechanism
Also, need to limit sigma's range
![[Pasted image 20230219232812.png]]

#### Correlated 
![[Pasted image 20230220110022.png]]





## Crossover
### Discrete
randomly select 1 parent's allele to inherite
![[Pasted image 20230220111859.png]]
### Intermediate
weighted average of 2 allele values from parents
The 3 ways of arithmetic crossover below, are all like intermediate
![[Pasted image 20230220111948.png]]
#### Single Arithmetic Crossover
replace **a single gene** with weighted average
![[Pasted image 20230220112231.png]]
#### Simple Arithmetic Crossover
It is different from the single arithmetic crossover
- weighted averaged all genes after index k
![[Pasted image 20230220112445.png]]
#### Whole Arithmetic Crossover
![[Pasted image 20230220112720.png]]





### Summary
![[Pasted image 20230220113032.png]]
- s1~s4: single arithmetic, alpha = 0.5
- w: whole arithmetic
- inner box: varied alpha
- outer box:blend crossover
## Multi-parent recombination
Several Ideas
### Segment and Recombine
![[Pasted image 20230220113404.png]]
### arithmetic
![[Pasted image 20230220113430.png]]
Note: just like 2 parent recombination, still divided into segement and arithmetic averaging