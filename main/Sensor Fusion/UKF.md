[[topic_Kalman Filter Special]]
****
The Unscented Kalman Filter is a variant of KF for non-linear cases.
Instead of random sampling, it deterministicly take samples to estimate the process's mean and covariance. The samples are _sigma points_
_sigma points_ are chosen in such a way that they capture the mean and the spread of the distribution in a way that is optimal in the sense of minimizing the error between the actual and the approximated distribution.
# UKF Algorithm
## Predict step
1. sigma points and their weights are generated
![[Pasted image 20230311154243.png]]
2. sigma points are passed through the process model, forming sigma points a time-step ahead![[Pasted image 20230311154442.png]]
3. Use _Unscented transform_ to compute prior's mean and covariance ![[Pasted image 20230311154509.png]]
The comparison with KF is here
![[Pasted image 20230311154636.png]]

## Update
1. convert to measurement with sigma points![[Pasted image 20230311160852.png]]
2. Use _Unscented transform_ to compute measurement (still sigma points here)'s mean and covariance (like in the previous step)![[Pasted image 20230311160925.png]]
3. Compute the Kalman Gain. Still, the Kalman gain is a balance between prediction and measurement ![[Pasted image 20230311161142.png]]
4. Compute new state estimate and covariance.![[Pasted image 20230311161445.png]]
An overview is here.
Instead of matrix in KF, the non-linear process in UKF is represented as functions
![[Pasted image 20230311161502.png]]

# A 2D linear example
In a linear process, there is no point in using UKF instead of KF. Just for demonstration.
## KF Implementation
To design a KF, specify the following:
```
x: state variables
F: process model
	x(k+1) = F*x(k)
H: measurement function
	prediction: H*x
R: measurement noise
Q: process noise
```
A recap on H: H convert the prior `x` to measurement by mutiplying.
![[Pasted image 20230311165051.png]]

![[Pasted image 20230311164452.png]]
![[Pasted image 20230311164508.png]]
![[Pasted image 20230311164523.png]]
## UKF Implementation
1. Determine the process function and measurement function.![[Pasted image 20230311165623.png]]
2. Specify the sigma points and their weights
3. The rest remains the same.
![[Pasted image 20230311165816.png]]




