[[topic_Kalman Filter Special]]
****
# Algorithm
## linearization
Non-linearity comes from 2 possible aspects: process model and measurement.
![[Pasted image 20230311214237.png]]
Note the linearization takes place at the current estimate.
The process model and measurement is linearized with Jacobian matrix.
![[Pasted image 20230311214323.png]]
![[Pasted image 20230311214403.png]]
![[Pasted image 20230311214513.png]]

## Radar tracking example
### modelling
![[Pasted image 20230311220341.png]]
![[Pasted image 20230311220352.png]]
![[Pasted image 20230311220406.png]]
The motion model is Newtonian. It is linear
![[Pasted image 20230311220428.png]]

### Linearize measurement model
Compute the Jacobian with respect to state variables
![[Pasted image 20230311220629.png]]
The result varies with epochs. The computed Jacobians are still functions of state variables.
![[Pasted image 20230311220704.png]]
