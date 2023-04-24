![[Pasted image 20230420105842.png]]
# Control law partitioning
partition into **model-based portion** and **servo portion**
model-based portion: `u = alpha*v + beta`
![[Pasted image 20230420105927.png]]
By aligning `u = alpha*v + beta` and the original motion model:
![[Pasted image 20230420110225.png]]
![[Pasted image 20230420110243.png]]
Now, with the new model: `e.. + k_v*e. + k_p*e = 0` a standard error equation is formed

# Performance specification
Standard form of a second order system
- zeta >= 1
- omega_n <= omega_res
![[Pasted image 20230420110711.png]]
![[Pasted image 20230420110804.png]]
This standard form can align with the closed-loop characteristics equation
getting `kv` and `kp`

# Disturbance Rejection
Note the steady state error is calculated with **end-value theorem**
![[Pasted image 20230420111602.png]]
Add **integral term** to eliminate ss error
![[Pasted image 20230420111548.png]]
Now, with integral term, e_ss == 0
