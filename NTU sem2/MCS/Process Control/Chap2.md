# Outline
![[Pasted image 20230218103933.png]]
![[Pasted image 20230218104129.png]]

# PID Controller
## General model
![[Pasted image 20230218104225.png]]
Note the relationship:
`K_C` is the proportional Gain
```
K_I = K_C / tau_I
K_D = K_C * tau_D
```
### 2DOF
Included a filter G_s to modify set point
![[Pasted image 20230218104344.png]]
## Effects of P, I, D
![[Pasted image 20230218104514.png]]

## Tuning Methods
### Trial & Error
Follow the order of P - I - D
Always find the sustained ocillation, marked with u
The final values are the ocillating values times some coefficients
![[Pasted image 20230218104730.png]]
### Continuous Cycling
#### Procedure
- start with steady state, eliminate I and D
- set `K_C` (proportional gain) to a small value
- introduce small set point change, gradually increase `K_C` until continuous cycling occurs. This K_C is known as _ultimate gain_, `K_cu`
- calculate the setting according to Z-N table
- 
![[Pasted image 20230218105036.png]]
![[Pasted image 20230218105044.png]]
Similar to the **trial-and-error** method above

### Intergral Error Criterion
The optimal settings minimizes the Integral Error Criterions
They all _integrate error over time_ in some form
- ![[Pasted image 20230224135141.png]]
- ![[Pasted image 20230224135207.png]]
# DSM
## Feedback system Model
Here we introduce `T(s)` and `R(s)`
`T(s)` is the TF _between output Y and reference R_
`S(s)` is the TF _between output Y and disturbance D_

![[Pasted image 20230218115931.png]]
*core thoughts:*
We want to derive `Gc(s)`, the **controller**
Thus, use T(s) equation
Solve for `Gc`
![[Pasted image 20230218120359.png]]

## First Order case
#recite The first order TF can be represented as:
![[Pasted image 20230224140028.png]]
![[Pasted image 20230317115416.png]]
`T(s) is the close-loop TF`
`T(s) == (Y/R)_d` as we provide a desired close loop function
```
T(s) = (Y/R)_d = exp(-theta*s) / (tau*s+1)
```
### No delay
if no delay, theta == 0
```
T(s) = (Y/R)_d = 1 / (tau*s+1)
```
substitute this to G_c expression (12-3b):
```
G_c(s) = (1 / G~(s)) * (1 / tau_c * s)
```
As a *first order system (no delay)*,
![[Pasted image 20230224140425.png]]
This is similar to PI control:
```
G_c(s) = K_C + K_I / s
```
### with delay (FOPTD)
Here, with time delay, `G~` is _different_
```
G~ = K*exp(-theta*s) / (tau*s + 1)
```
Using Taylor Series, linearize it as:
```
exp(-theta*s) = 1 - theta*s
G~ = K*(1 - theta*s) / (tau*s + 1)
```
Substitute this to 12-3b, gives us:
*Different G~ still leads to a format in PI controller*
![[Pasted image 20230224141210.png]]
First order with time delay

## Summary
### Plants without delay
Note that for both 1st order and 2nd order, `(Y/R)_d` remains the same of 1st order expression
Order difference reflects on plant `G(s)`
This also leads to different controller `G_c(s)`
#recite 
![[Pasted image 20230224153215.png]]
### Plants with delay
time delay reflects on `(Y/R)_d`
nominator turns to exp(-theta_c·s) from 1
![[Pasted image 20230224153536.png]]
### Common
expression for calculating G_c(s) is the same:
```
G_c = 1/G~ * ((Y/R)_d/(1-(Y/R)_d))
```
![[Pasted image 20230224153943.png]]
Different order leads to different G~
Different Time delay leads to different `(Y/R)_d`

# [[IMC]]
# Smith Predictor
Keys:
- process model G~(s) is divided into 2 parts: with time delay and without time delay
- Y1~ is the predicted response
- predicted process output is also delayed by `theta1~`. This is compared with actual output Y
![[Pasted image 20230224162848.png]]

