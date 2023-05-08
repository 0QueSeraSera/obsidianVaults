# Force control
Consider both force and position control
![[Pasted image 20230422202221.png]]
with the original model: `mx.. + f = tau`, need to acquire controllable form
still, by replacing `tau` with `av+b`
![[Pasted image 20230422202301.png]]
introduce a auxillary var: `e_f`
with `e_f = f_d - f` and `v = f../k_e`
_design_ the controller
the controller than becomes the std 2nd form
![[Pasted image 20230422203503.png]]

# Hybrid Position/Force Control
![[Pasted image 20230422204043.png]]
## Example
![[Pasted image 20230422204227.png]]
Still apply this `av+b` alignment
![[Pasted image 20230422204334.png]]
Acquire Position control and force control _separately_.
Recall that `x.. = v1`, `y.. = v2` 
Position Control:
	`e = y_d - y`
	`e.. + k2v*e. + k2p*e = 0`
Force Control
	`e_f = f_d - f`
	`v1 = (f_d.. + k_1v*e_f. + k_1p*e_f) / k_e`

![[Pasted image 20230422204618.png]]

## General Form
![[Pasted image 20230422205340.png]]
![[Pasted image 20230422205401.png]]
