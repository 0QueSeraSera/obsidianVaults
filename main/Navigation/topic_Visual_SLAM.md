[[root_Navigation_Stack]]
****
[[6 Non-linear Optimization]]
[[7 Visual Odometry 1]]
[[9 Backend1]]
[[10 Backend2]]
[[11 Loop Closure Detection]]
[[12 Mapping]]
# Overview
![[Pasted image 20230305142752.png]]
![[Pasted image 20230305142800.png]]

## Concepts
Visual Odometry
	- Visual Odometry #VO estimates the _camera's movement_ and revover _spatial info_ based on adjacent frames. It only keeps temporary logs
	- The error will accumulates (**Accumulating Drift**)

Optimization
- the estimate from VO carries noise. 
- Backend is essentially the Maximum-a-Posteri #MAP 
- ![[Pasted image 20221122023159.png]]
Loop Closure Detection
![[Pasted image 20230305144458.png]]

## Mathmetical Representation
at discrete time instant t = 1, 2, ..., K,
robot's positions are: x_1, x_2, ..., x_K
There are N landmarks: y_1, ..., y_N
![[Pasted image 20230305145117.png]]

Motion Equation:
```
x_k = f(x_k-1, u_k, w_k)
```
![[Pasted image 20230305150736.png]]
Observation Equation:
![[Pasted image 20230305145510.png]]
```
z_(k,j) = h(y_j, x_k, v_(k,j))
```
![[Pasted image 20230305145628.png]]
![[Pasted image 20230305150639.png]]
Given `u` and `z`, estimate `x` (localization) and mapping (`y`)
