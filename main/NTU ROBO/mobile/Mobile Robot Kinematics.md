# Kinematics Model and Constraints
## Frame Setup
Set up the reference frame
![[Pasted image 20230423152332.png]]
A point on the robot contains its global frame coord and heading
a vector 3x1
![[Pasted image 20230423152540.png]]
![[Pasted image 20230423152728.png]]
### Example
local v is acquired from global v
`v_local = R(theta) X v_global`
![[Pasted image 20230423153000.png]]

## Forward Kinematics
![[Pasted image 20230423153230.png]]
![[Pasted image 20230423153329.png]]
### Differential Drive robot
It follows a circle path, according to arc length:
![[Pasted image 20230423154249.png]]

With this property, express the velocity in local frame first
![[Pasted image 20230423154435.png]]
The local speed can be transformed with wheel speed and geometric params
![[Pasted image 20230423154605.png]]

## Constraints
### Fixed Standard Wheel
![[Pasted image 20230423155003.png]]
![[Pasted image 20230423194804.png]]
Both rolling and sliding constraints are on the **local frame**
Rolling constraint: wheel motion axis (yellow)
- rolling velocity: `Phi. * r`
- global velocity `R(theta) X xi_I. == xi_R.` projects onto local frame. 
**Remember the sign**:
`[S(a+b), -C(a+b), -lC(b)] .* [x. y. theta.] - r * Phi. = 0`
![[Pasted image 20230423201303.png]]
Sliding constraint: vertical to wheel motion axis (red)
The signs are all positive.
don't forget the effect of `l` and `theta`
#### Example
![[Pasted image 20230423161926.png]]
### Steered Standard Wheel
![[Pasted image 20230423162124.png]]
### Castor Wheel
![[Pasted image 20230423162342.png]]
![[Pasted image 20230423201633.png]]
Note that `beta` is variable. all signs in sliding constraint are **positive**.
### Swedish Wheel
![[Pasted image 20230423202112.png]]
![[Pasted image 20230423202131.png]]

## Summary
![[Pasted image 20230423202250.png]]
Fusing
![[Pasted image 20230423203328.png]]![[Pasted image 20230423203329.png]]
Example
![[Pasted image 20230423202621.png]]
![[Pasted image 20230423204211.png]]
Wrap these up:
Note that the two sliding constraints are the same, one gets removed.
![[Pasted image 20230423204636.png]]