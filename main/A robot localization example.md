[[Kalman Filter Special]]
****
Apply EKF and UKF to this example. Compare their differences.
# Scenario
## Kinematics
![[Pasted image 20230311222207.png]]
Use a **bicycle model** to simulate:
![[Pasted image 20230311222831.png]]
![[Pasted image 20230311222848.png]]
![[Pasted image 20230311222900.png]]

# UKF Solution
## State variables design
note the difference between `theta` and `alpha`. the former is robot's orientation, more like its own status. the latter is the heading, a control input.
![[Pasted image 20230311223111.png]]
## System Model
A non-linear motion model with white noise
```
x_bar = x + f(x, u) + N(0, Q)
```
![[Pasted image 20230311223832.png]]
Note the time interval should be small.
![[Pasted image 20230311223908.png]]
larger time interval increases the non-linearity

## Measurement Model
![[Pasted image 20230311224043.png]]
![[Pasted image 20230311224538.png]]
![[Pasted image 20230311224602.png]]
