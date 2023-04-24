[[Chap4 Representation Mutation & Recombination]]
****
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
Cannot arbitrarily alter gene values, must **change at least 2 values**.
mutation param: the probability that an operator is applied once to the _whole string_. 
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
preserve relative order
![[Pasted image 20230220115226.png]]
Transmit ***relative order*** from the ***2nd parent***
![[Pasted image 20230220115724.png]]
Example:
a part of p1 is selected: 4567
**not used digits: 12389**
check their _appearance order_ in _p2_: 1 9 3 8 2
	the order **starts counting at the tail** of the segment:
	search space: _1_ 4 _9_ _3_ 7 _8_ _2_ 6 5
![[Pasted image 20230421180645.png]]
## Partially mapped crossover (PMX)
https://www.youtube.com/watch?v=EZg-l2FF-JM&t=207s
![[Pasted image 20230220125328.png]]


## Cycle Crossover
https://www.youtube.com/watch?v=e7ozr4sARyI
![[Pasted image 20230423112551.png]]
Note that odd cycles are copied from parent1, even cycles are from parent 2
![[Pasted image 20230423105543.png]]
![[Pasted image 20230423105603.png]]

## Edge Recombination
![[Pasted image 20230421204636.png]]
![[Pasted image 20230421205849.png]]