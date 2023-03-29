[[topic_modern control basics]]
# defination
#state_space_model
a state-space model of a system:
- minimum set of internal variables
- system input
- initial time t_0
be able to predict the future states and outputs
state-equations:
a set of first-order-differential equations
![[Pasted image 20221123135038.png]]
a standard form:
![[Pasted image 20221123135106.png]]

# transfer function from state_space_model 
from 1.1 and 1.2:
```
sX(s) = AX(s) + BU(s)
Y(s) = CX(s) + DU(s)
--->
X(s) = inv([sI - A])BU(s)
--->
Y(s) = (C*inv([sI - A])B + D)U(s)
--->
G = Y/U = C*inv([sI - A])B + D
```
==**G = Y/U = C inv([sI - A]) B + D**==
the denominator of G is `det([sI-A])`
The **poles** of the system is the same with A's **eigenvalues**

# solution of state vector
==important!!!==
_include x(0) here:_
```
sX(s) - x(0) = AX(s) + BU(s)
X(s) = inv(sI-A).x(0) + inv(sI-A).BU(s)
```
from `X(s)` solve for x(t)
```
x(t) = Phi(t).x(0) + gamma(t)
```
![[Pasted image 20221123140619.png]]
## state tansition equation
![[Pasted image 20221123140828.png]]


