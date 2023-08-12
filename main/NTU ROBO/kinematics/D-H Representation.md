[[2. Kinematics]]
****
Describe transformation between adjacent frames with **single standard homo-coord transformation matrix**
![[Pasted image 20230221210731.png]]
# Algorithm
## 1. Init:
![[Pasted image 20230421220254.png]]
Rules:
![[Pasted image 20230421220404.png]]
Tool tip:
![[Pasted image 20230421220508.png]]
z <--> approach vector; y <--> sliding; x <--> normal
### Example
A partial example![[Pasted image 20230421220738.png]]
normally put z0 towards other parts, x0 has 2 choices.
intersection of z0 and axis 1 is next frame's origin.
x1 _must be orthogonal_ to z0 and z1. y1 is then determined
![[Pasted image 20230421220907.png]]
## 2. Determine Kinematics Parameters
4 params in the table: theta, d, a, alpha
`theta, d`: x axis angle and distance (_along and about the previous z_)
`a, alpha`: z axis angle and distance (_along and about the new z_)
![[Pasted image 20230421221504.png]]
### Example continued
`theta`: angle of x axis: theta1
`d`: fixed, d1
`a`: fixed, 0
`alpha`: angle of z axis, fixed to pi/2, but what **sign**?
**About the x1 axis**, right hand rule, hence -pi/2