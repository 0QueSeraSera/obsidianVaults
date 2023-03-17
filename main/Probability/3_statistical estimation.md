[[Bayes Theory]]
****
# background
from [[Bayes Theory]]
![[Pasted image 20221121170730.png]]
The pdf is often unknown, thus use estimation
#posterior is hard to estimate
instead, reach out to #priori and #class_conditional_probability 
#priori estimation:
![[Pasted image 20221121171024.png]]
# non-param approach
![[Pasted image 20221121171350.png]]
#priori `P` is from frequency, assume pdf `p(x)` is uniform: 
`P(x)约等于p(x)V`
## kernel's effect
![[Pasted image 20221121171746.png]]
fall criteria:
each sample's every dimension, the abs distance is smaller than h/2
## Parzen Window
![[Pasted image 20221121172004.png]]
![[Pasted image 20221121172026.png]]
![[Pasted image 20221121172036.png]]
- K(·) is the parzen window function
- replace u with (x-x_i)/h
Now with the number of falling in the kernel/cell: `k`
recall that:
	`p(x)=k/(nV)`
	`V=h^d`
estimated p(x):
![[Pasted image 20221121172316.png]]
#### example
![[Pasted image 20221121172657.png]]
note that in parzen window's function, ==**x** is the location of the estimated pdf==
in this case, x = y = 3, 10, 15
reminder:
**u** is a vector and needs to gaurantee every dimension
![[Pasted image 20221121172836.png]]

## kNN estimation
![[Pasted image 20221121173521.png]]
Parzen fix V, count k
kNN fix k, calculate V
==same principal:==
`p(x) = k/(nV)`

### posterior estimation with kNN
![[Pasted image 20221121174740.png]]
![[Pasted image 20221121174756.png]]
![[Pasted image 20221121174814.png]]
with kNN, the frequency k_i/k is associated with observation **x**, depends on **x**, the frequency is #posterior 
### NN rule
![[Pasted image 20221122023917.png]]
#NN_rule
#decision_rule 

# param approach
## maximum likelihood
![[Pasted image 20221122024946.png]]
D is a set of training sample
#MLE #likelihood_of_theta 
![[Pasted image 20221122025041.png]]
solution:
![[Pasted image 20221122025356.png]]
### multi-variate Gaussian case

![[Pasted image 20221122025531.png]]
![[Pasted image 20221122025543.png]]
![[Pasted image 20221122025559.png]]
