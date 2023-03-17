[[analysis of the discrete control system]]
****
# setup:
![[Pasted image 20221031203724.png]]
characteristic equation (CE):
P(z) = 1 + G(z)H(z) = 0
```
To be stable, all roots of CE must be inside the unit circle
```
critical stability:
![[Pasted image 20221125162215.png]]

# Stability judgement
## Jury test
`directly apply in Z domain
`similar to Herwitz`
### setup
![[Pasted image 20221031204313.png]]
2nd row is the coefficients aligned with its order
1st row reverse the 2nd row 
**remember to list z powers from n to 0**
![[Pasted image 20221031204559.png]]
### judgement
![[Pasted image 20221031204648.png]]

## Routh test with Bilinear Transformation
### bilinear transformation
`inside unit circle in Z plain <--> LHP in w plain`
`z = (w+1)/(w-1); w = (z+1)/(z-1)`
![[Pasted image 20221031205142.png]]
`
`
## summary
![[Pasted image 20221031205249.png]]

[[analysis of the discrete control system]]
****
# Transient and Steady-State response
## concepts
![[Pasted image 20221031214903.png]]
![[Pasted image 20221031215154.png]]


## steady-state error analysis
![[Pasted image 20221031215417.png]]
![[Pasted image 20221031215604.png]]
**Key: represent E(z) in terms of G, H and R, not with output**
![[Pasted image 20221031215615.png]]
e_ss uses final value theorem, contains an `(1-z^-1)`
#final_value_theorem
==key idea: use final value theorem to get e_ss==
### position, velocity, acceleration error constant
**note: error is R(z) - B(z), not R(z) - C(z)**
#### static position error constant
input: unit step
`R(z) = 1/(1 - z^-1)`
along with
`e_ss = lim(z->1){(1 - z^-1) * 1/(1 + GH(z) * R(z))}`
define:
	`K_p = lim(z->1){GH(z)}`
we have:
	`e_ss = 1/(1 + K_p)`
#### static velocity error constant
![[Pasted image 20221031220139.png]]
#### static acceleration error constant
![[Pasted image 20221031220155.png]]

#### summary
![[Pasted image 20221031220333.png]]