[[topic_modern control basics]]
****
# background
plant:
![[Pasted image 20221123174952.png]]
performance index:
![[Pasted image 20221123175009.png]]
time interval of interest:
	`[i,N]`
problem setup:
Find the control u*(k) in `[i,N]` that drives the system along a trajectory `x*(k)` such that **performance index is minimised**
## some performance indices
### minimum time
minimize the time for a system to reach desired final state zeta from x(0)
![[Pasted image 20221123175355.png]]
### minimum fuel
fuel is **propotional to the magnitude of control vector**
![[Pasted image 20221123175534.png]]
### minimum engery
with fixed control, minimize the energy of the final state and all intermediate states
![[Pasted image 20221123175722.png]]
with L, phi respectively:
![[Pasted image 20221123175801.png]]
balancing:
![[Pasted image 20221123175855.png]]

# dynamic programming
## Bellman's principle of optimality
#Bellman 
![[Pasted image 20221123180112.png]]
key: ==irrelavant== to previous control, the ==remaining decisions== must constitute an ==optimal== policy
## discrete system application
use Bellman Principle to find u*(k)
plant and performance index:
![[Pasted image 20221125111551.png]]
suppose for `[k+1, N]`, we have known _all_ optimal info, including ==cost and control for each state ==
use an **arbitrary control u(k) at ==time k**== and this **known optimal control sequence ==from k+1 on==**, the cost:
![[Pasted image 20221125111902.png]]
According to #Bellman 
![[Pasted image 20221125112050.png]]
note: already know `[k+1, N]` before, now it is `[k, N]`
The **time k's optimal u*(k)** is to minimize 22.6

# LQR with DP
## defination:
![[Pasted image 20221125112514.png]]
find the optimal u*(k) on `[i,N]` that minimizes `Ji`
## backward derivation
At `k=N` ==(working backwards from known last state)==
(a quadradic form around S(N))
`J_N* = 1/2 · xT(N)S(N)x(N) 
![[Pasted image 20221125112819.png]]
### 1_get_u*(N-1)
onestep back! from N to N-1:
```22_10
J_N-1 = 1/2 · xT(N)S(N)x(N)
	+ 1/2xT(N-1)Qx(N-1)
	+ 1/2uT(N-1)Ru(N-1)
```
replace x(N):
![[Pasted image 20221125113352.png]]
after the derivative, we have:
![[Pasted image 20221125113545.png]]
define the coeff of x(N-1) as K(N-1)
![[Pasted image 20221125113601.png]]

### 2_get_J_N-1*
sub u*(N-1) to 
![[Pasted image 20221125114253.png]]
similarly, we have a quadradic form:
![[Pasted image 20221125114452.png]]
## the general recursive form
![[Pasted image 20221125114105.png]]
K(k) and S(k) no need to recite
will be provided
# Riccati difference equation
previously, we use this two equations for #Bellman optimality
![[Pasted image 20221125115928.png]]
Riccati equation
![[Pasted image 20221125115949.png]]
It can be proved that when N->inf, gains in K(k) becomes constant. S(k) = S(k+1) = const = S_hat
then we have Riccati equation
![[Pasted image 20221126002712.png]]
Solution S_hat: recursion or eigen method
