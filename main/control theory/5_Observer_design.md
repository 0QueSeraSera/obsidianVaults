[[topic_modern control basics]]
****
gives estimates of system from inputs and measured outputs
**the estimated states will replace the true states in the feedback controller**
## Prediction Observer
- ![[Pasted image 20221124164104.png]]
- the estimate is based on one step before
### block diagram
![[Pasted image 20221124165132.png]]
### Open-loop Observer
![[Pasted image 20221124163526.png]]
![[Pasted image 20221124163558.png]]
application scenario:
stable systems
![[Pasted image 20221124163633.png]]

### Closed-loop Observers
similar to the block diagram's case
![[Pasted image 20221124163713.png]]
To determine estimate `x_(k+1)`, check `x_(k)`'s expression
_line1 will be provided_
**derive line2**
```
line1 x_(k+1) = Ax_(k) + Bu(k) + Lo(y(k) - Cx_(k))
line2  = [A-LoC]x_(k) + Bu(k) + Lo·y(k)
```
![[Pasted image 20221124165920.png]]
### x_e(k) **additional, crucial for understanding**
`x_e(k+1) = [A - Lo·C]x_e(k)`
thus, `alpha(z) = det(zI - A + Lo·C)`
![[Pasted image 20221127211734.png]]

### pole placement design
Observer Poles:
```
det([zI - A + Lo·C]) = 0
```
contrast with feedback controller case:
```
alpha(z) = det([zI - A + BK]) = 0
```
Similarly, study the poles of observer
![[Pasted image 20221124170209.png]]
very much alike pole placement in [[4_controller_design]]

### Ackermann's formula
recall the controller case
![[Pasted image 20221124171834.png]]
![[Pasted image 20221124171854.png]]
## reduced-order Observers
a lower order observer to estimate unmeasurable states
### setup
divide into measurable and unmeasurable parts:
x_b(k+1):
![[Pasted image 20221124172355.png]]
x_a(k+1):
![[Pasted image 20221124172637.png]]
Compare with the full-order observer:
![[Pasted image 20221124172820.png]]
a mapping relation:
![[Pasted image 20221124172845.png]]
Note: no Ackermann mentioned for reduced order observer

### interpretation
To understand the mapping of reduced order observer
![[Pasted image 20221124224525.png]]
from the defination:
![[Pasted image 20221124224606.png]]
Focus on x_b:
`x_b(k+1) = A_ba·x_a(k) + A_bb·x_b(k) + B_b·u(k)`
==view x_b as state vector x==
**set this whole block `B_b·u(k) + A_ba·x_a(k)` as Bu(k)**
```
x <--> x_b
A <--> A_bb
Bu(k) <--> B_b·u(k) + A_ba·x_a(k)
```
For y's equation:
expand x_a:
`x_a(k+1) = A_aa·x_a(k) + A_ab·x_b(k) + B_a·u(k)`
again, x_b --> x, compare with`y(k) = Cx(k)`
```
C <--> A_ab
y(k) <--> x_a(k+1) - A_aa·x_a(k) - B_a·u(k)
```
These substitutions apply to ==full order observer model==
#6203_recite 
```
x_(k+1) = Ax_(k) + Bu(k) + Lo(y(k)-Cx_(k))
```
![[Pasted image 20221124225840.png]]
### design **more natrual to use pole placement 17.6**

![[Pasted image 20221124173323.png]]
Ackermann:
![[Pasted image 20221124173329.png]]
#6203_recite 
summary on Ackermann:
- directly compute K/Lo
- Lo's formula is sort of the transpose of K
	- `[0 0 ... 1]` got transposed
	- alpha_c(A) and alpha_o(A)'s postion is exchanged

## current Observers
estimates the states at kth instant by measurement from kth instant
**sub 18.1 into 18.2, will lead to an additional A**
![[Pasted image 20221124173829.png]]
its x_(k+1) expression:
![[Pasted image 20221124174058.png]]
contrast with prediction observer
![[Pasted image 20221124174311.png]]


