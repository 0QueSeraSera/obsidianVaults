# Single Link 
![[Pasted image 20230420111914.png]]
Derive the model from _Lagrange equation of motion_
`L = K - P`
`d/dt{dL/dtheta.} = tau + dL/dtheta`
![[Pasted image 20230420112350.png]]
![[Pasted image 20230420112600.png]]

# Two-link polar robot
![[Pasted image 20230420140938.png]]
The status variables are packed in vectors.
tau means _torque_ here
![[Pasted image 20230420141102.png]]
![[Pasted image 20230420141415.png]]
![[Pasted image 20230420141623.png]]

# n-links
The component of M, C and g, tau are common.
![[Pasted image 20230420142033.png]]
## non-linear control
Review the SISO partition method
![[Pasted image 20230420142254.png]]
![[Pasted image 20230420142308.png]]

The case for MIMO
still, align `alpha*v + beta` with `f{M,C,g,theta}`
and `v <--> theta..`
![[Pasted image 20230420142519.png]]
### PD controller
![[Pasted image 20230420142839.png]]
Even though it is in matrix form, `Kp` and `Kv` are diagonal and can be decoupled.
