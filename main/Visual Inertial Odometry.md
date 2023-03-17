[[Navigation Stack]]
****
# Overview1
https://arxiv.org/abs/1906.02650
## Model
### IMU kinemetic model
state vector `x` contains IMU state `x_I` and feature position `G^p_f`
```
x_I contains:
	a unit quaternion: rotation from the global frame to IMU frame
	IMU position and velocity
	gyroscope and accelerometer biases
```
In summary, IMU state `x_I` has IMU frame position, velocity and rotation, and bias of the gyroscope and accelerometer
![[Pasted image 20230311204927.png]]
![[Pasted image 20230311210135.png]]
![[Pasted image 20230311210444.png]]
...
### Camera Measurement Model
![[Pasted image 20230311210707.png]]
![[Pasted image 20230311210722.png]]

## State Estimation
### Filtering-based and Optimization-based estimation
![[Pasted image 20230311210856.png]]
MSCKF and filtering-based estimation
advantage:
	high accuracy
disadvantage:
	requires one time linearization
![[Pasted image 20230311211116.png]]

### Tightly-coupled and loosely-coupled fusion
![[Pasted image 20230311211518.png]]
![[Pasted image 20230311211526.png]]
Tightly-coupled: process inertial and visual measurement loosely. _Efficient_, but decoupling causes **information loss**.
loosely-coupled: directly fuse visual and inertial measurement. _More accurate_.


# Overview2
## model
### IMU model
![[Pasted image 20230312154900.png]]
![[Pasted image 20230312154954.png]]
Measurement model and System equations are seperate. IMU's Measurement model describes Gyroscope and Accelerometer's reading.
system equations describe IMU's motion as a whole
### Camera Model
![[Pasted image 20230312155226.png]]


# Overview3
![[Pasted image 20230312155729.png]]
![[Pasted image 20230312155759.png]]
![[Pasted image 20230312160032.png]]
![[Pasted image 20230312160201.png]]
