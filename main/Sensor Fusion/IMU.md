# IMU
IMU consists of a _magnetometer_, a _accelerometer_, and a _gyro_
To estimate attitude/ orientation, magnetmetor + accelerometer forms a solution, gyro alone forms a solution.
Both solutions have their advantages and drawbacks.
![[Pasted image 20230309115649.png]]
## Acc + Mag
## principles
Readings provide some directions directly.
![[Pasted image 20230309120037.png]]
When the object is static, the ACC provides `Down`, MAG provides a direction between `North` and `Down` (the angle differes in different regions)
Use cross product to get other directions.
![[Pasted image 20230309120301.png]]
## Problems and Calibration
1. Accelerometer measures all linear accelerations.  When object is **moving**, "Down" is inaccurate.
			Rotation will also cause this problem (Accelerometer not at the center of rotation)
2. Magnetometer is affected by nearby magnetic field
### Magnetometer calibration
![[Pasted image 20230309120522.png]]
Magnetic source can be divided into hard and soft.
Hard iron source produces offset. Soft iron sources provides skewness
![[Pasted image 20230309120626.png]]
Calculate the skew and translation factor
## Gyro
Essentially integrating gyro's reading. #dead_reckoning
**drawback**: 
- requires the initial orientation
- gyro has bias and random noises.
	- integration mitigates random noises to some extend
	- but bias cannot be cancelled.
![[Pasted image 20230309115728.png]]



# Include GPS
![[Pasted image 20230309120826.png]]
GPS provides position info in a broad picture. Its error is large and the frequency is low. IMU provides #dead_reckoning between GPS updates.