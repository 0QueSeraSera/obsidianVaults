[[topic_modern control basics]]
****
# Canonical Forms
Controllability matrix `Wc`
![[Pasted image 20221123163045.png]]
us similarity transform to CCF:
![[Pasted image 20221123163227.png]]
Controllability matrix becomes:
![[Pasted image 20221123163254.png]]
Ac, Bc and P are:
![[Pasted image 20221123163319.png]]
#6203_recite
A comparison with OCF
![[Pasted image 20221123164050.png]]
1. attention to the coefficient, z^n + a_n-1.z^(n-1) + ...a_0, z^n does not count as a coeff in both Ac and Ao
2. composition of P and Q is different
3. Cc and Bo is calculated from similarity transorm matrix
## example
![[Pasted image 20221127204112.png]]
#### step1 calculate characteristic poly **det(zI - A)**
![[Pasted image 20221127204258.png]]
#### step2 write Ac from characteristic poly's coeff **important**
![[Pasted image 20221127204403.png]]
#### step3 calculate Wc~
`Bc === [0;1]`
`Wc~ = [Bc A·Bc]`
`P = Wc · inv(Wc~)`
#### step4 calculate Cc _CC=CP, CCCP_

# controllability
#controllability
defination: 
==**reach arbitrary states**==
![[Pasted image 20221123164755.png]]
criteria:
```
rank(Wc) == n
```
# observability
#observability
_ability to determine the initial state x(0) based on initial state x(0)_
![[Pasted image 20221123165542.png]]
`rank(Wo) == n`
# relationship between ctrb and obsv and transfer function
## principles
- if the transfer function has **pole-zero cancellation**, the system cannot be both ctrb and obsv
- otherwise, if no pole-zero cancellation, system can always be completely ctrb and obsv
note: the same TF with different ABCD combinations can have different results




## sampling effect
recall the transformation between (A, B, C, D) and discrete case[[2_discrete_state_space]]
![[Pasted image 20221123171915.png]]
![[Pasted image 20221123171926.png]]
