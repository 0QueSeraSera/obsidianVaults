[[MPC]]
****
Components of MPC
![[Pasted image 20230316214135.png]]
# Example
![[Pasted image 20230316214706.png]]
## A naive solution
![[Pasted image 20230316214723.png]]
## Another case
![[Pasted image 20230316215305.png]]
## More complicated input
![[Pasted image 20230316215509.png]]
![[Pasted image 20230316215640.png]]

# Basics
![[Pasted image 20230316215709.png]]

Apply the state-space model:
![[Pasted image 20230316220206.png]]

In matrix format, expand the control signal:

![[Pasted image 20230316220413.png]]

This combines the past and the future:

![[Pasted image 20230316220525.png]]

More compact version:
![[Pasted image 20230316220542.png]]
## Cost Function
2 goals:
- let output follow a desired reference signal
- minimises the control effort
J has 2 terms, representing these two. A coefficient is setup to balance the weight.
![[Pasted image 20230316220931.png]]
## Obtain the control law
![[Pasted image 20230316223348.png]]
