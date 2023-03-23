# Cpp case
## methods to pass a vector
### 1.pass by value
**Does not** change the original vector
**not efficient**
**no extra declaration** like "&"
![[Pasted image 20230318105749.png]]
### 2.reference
can modify the argument outside the function
![[Pasted image 20230318110120.png]]

### 3. const reference

![[Pasted image 20230318110153.png]]

### 4. pointer
like reference, can also affect the original param
![[Pasted image 20230318110437.png]]

## pointer vs reference
common:
1. can modify the original argument
2. avoid making a entire copy
difference:
1. different declaration in _formal parameter (形参)_, pointer's _actual parameter_ is passed with '&' as address
2. access method
3. Safety: Pointers can be null, reference cannot.
	*this makes reference safer*
![[Pasted image 20230318110541.png]]

A usage example:
![[Pasted image 20230318111448.png]]


# Python case
