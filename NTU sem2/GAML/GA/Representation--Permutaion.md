# Overview
tasks:
- **arranging** with certain **order**
- ![[Pasted image 20230220113754.png]]
- A list of n integers, **each only occurs once**
## Example: TSP
To find the minimum length of travelling all cities (_arranging order_)
each city _occurs only once_
![[Pasted image 20230220113906.png]]
# Mutation
Cannot arbitrarily alter gene values
Affects the whole string
![[Pasted image 20230220114300.png]]
## Swap mutation
![[Pasted image 20230220114410.png]]
## Insertion mutation
![[Pasted image 20230220114455.png]]
## Scramble mutation
![[Pasted image 20230220114534.png]]
## Inversion mutation
like scramble mutation, this also acts on sub string
Also **preserves adjacency** info
![[Pasted image 20230220114625.png]]

# Crossover
![[Pasted image 20230220114857.png]]
like mutation, need to prevent **inadmissible** solutions (repeated genes, etc.)
## Order 1 crossover
![[Pasted image 20230220115226.png]]
Transmit ***relative order*** from the ***2nd parent***
![[Pasted image 20230220115724.png]]
## Partially mapped crossover (PMX)
![[Pasted image 20230220125328.png]]


## Cycle Crossover
