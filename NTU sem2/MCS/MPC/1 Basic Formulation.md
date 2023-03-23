[[MPC]]
****
Components of MPC
**internal model**
**reference trajectory (close loop)**
**receding horizon**
**optimization**

![[Pasted image 20230316214135.png]]
# Example
![[Pasted image 20230316214706.png]]
**view z as a time shift symbol: zY <--> y(k+1)**
## A naive solution
Note: _hat notation_ means prediction
`y_hat(k+2|k)` means prediction of 2 steps forward _at time k_
![[Pasted image 20230323105506.png]]
## Another case
Now, there are 2 constrains, only approximate solution
![[Pasted image 20230316215305.png]]
## More complicated input
![[Pasted image 20230316215509.png]]
![[Pasted image 20230316215640.png]]

# Basics
```
obtain the measurement
required input
apply the required input
```

![[Pasted image 20230316215709.png]]
## State-Space Formulation
Apply the state-space model:
y is **predicted**, thus with the hat notation
![[Pasted image 20230322213541.png]]

In matrix format, expand the control signal:
The control signals form iterative relation:
`u(k) = u(k-1) + delta{u(k)}`
`u(k+1) = u(k-1) + delta{u(k)} + delta{u(k+1)}`
![[Pasted image 20230322213646.png]]

This combines the _past_ and the _future_:

![[Pasted image 20230316220525.png]]

More compact version:
![[Pasted image 20230316220542.png]]
With 3 coefficients being:
![[Pasted image 20230322215847.png]]

## Cost Function
2 goals:
- let **output follow a desired reference signal**
- **minimises the control effort**
J has 2 terms, representing these two. A _coefficient_ `lambda` is setup to balance the weight.
![[Pasted image 20230316220931.png]]
## Obtain the control law
To find the control law, follow one of the criteria: **minimizes the cost function**
The _predicted output_ `y_hat(k+i|k)` is expressed with past values of IO and future control signal
`Y^ = F^ + GU^`
![[Pasted image 20230316223348.png]]

Try to relate cost function `J` with control effort `u`
![[Pasted image 20230320112126.png]]
## Receding horizon strategy
**Receding horizon** is about repeatedly solving the optimization problem, rather than solving by once.
only the first control signal is applied to the system
![[Pasted image 20230320113246.png]]
![[Pasted image 20230320113637.png]]
# Unconstrained MPC
## Structure

![[Pasted image 20230320114459.png]]
Relate the MPC controller with the formula before:
![[Pasted image 20230322212423.png]]

The matching is shown here:
![[Pasted image 20230322212630.png]]

## Many State Representation
An incremental input:
![[Pasted image 20230322215940.png]]
compared with (1):
![[Pasted image 20230322220034.png]]



