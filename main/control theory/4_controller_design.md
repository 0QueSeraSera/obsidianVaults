[[modern control basics]]
****
# state feedback design
linear state feedback case
![[Pasted image 20221123172036.png]]
```
u = -Kx(k)
x(k+1) = [A-BK]x(k)
zX(z) = [A-BK]X(z)
```
characteristic polynomial:
#6203_recite alpha(z) is from the det, but ==**alpha_c(z) is from poles decomposition**==
```
alpha(z) <--> det([zI-A+BK])
alpha_c(z) <--> (z-p1)(z-p2)……
equate alpha(z) and alpha_c(z) to solve
```
## pole placement method
![[Pasted image 20221123172335.png]]
(A, B) needs to has #controllability to arbitrarily place poles
key idea: ==**aligning alpha(z) and alpha_c(z)**==
```
alpha_c(z) = (z-p1).(z-p2)...
```
Zeros are not changed with linear feedback



## Ackeramnn's Formula
we already have alpha_c(z):
```
alpha_c(z) = (z-p1).(z-p2)...
alpha_c(z) = z^n + beta1.z^(n-1) + ... + beta_n
```
Ackermann's formula:
#6203_recite 
![[Pasted image 20221124160544.png]]
==sub A to z in alpha_c(z)==
```
alpha_c(A) = A^n + beta1·A^(n-1) + ... + beta_n·I
```
Ackermann obtain K directly with 12.1, no alignment like pole placement method

# deadbeat control
## background
![[Pasted image 20221124161054.png]]
deadbeat control:
close-loop system arrive and remain at rest in ==at most n sampling periods==
## criteria
all poles at the origin
![[Pasted image 20221124161424.png]]
deadbeat controller:
**key: `alpha_c(z) = A^n`**
![[Pasted image 20221124161506.png]]
