# Overview
Aim: **To form a desired close loop transfer function**
This will be shown in different characters of the controlled variable (slow/fast, steady/oscillatory)
![[Pasted image 20230219210334.png]]
With a controller Gc and plant Gp:
The **desired** `Y(s) / R(s)` is equal to:
![[Pasted image 20230219210619.png]]
```
Gp·Gc / (1 + Gp·Gc)
```
In DSM, `Y(s) / R(s)` is known, and _Gp_ is Known
And to solve for Gp:
![[Pasted image 20230219210926.png]]

# First Order