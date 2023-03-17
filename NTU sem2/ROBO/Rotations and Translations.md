[[Kinematics]]
****
# Basic Concepts
**Rotation Transformation Matrix**
![[Pasted image 20230219161808.png]]

**Fundamental Rotation Matrix**
M: _mobile_ frame, F: _fixed_ frame
Fundamental Rotation Matrix: rotate M about F's unit vector
![[Pasted image 20230219162048.png]]

# 3 ways of fundamental rotation
rotate M about `f1, f2, f3` respectively
![[Pasted image 20230219162451.png]]
Rotate above m1.
`rotate from v1 to v2, with the angle of theta, the factor is cos(theta)`
Note the correlation:
elements on the diagonal: `f_i --> m_i`
`f1` is irrelevant with `m2, m3`
`m1` is irrelevant with `f2, f3`
Thus, first row and first col are 0
![[Pasted image 20230219162826.png]]
Similarly, rotation about f2 and f3
![[Pasted image 20230219163629.png]]
### pattern
Summary:
- elements on the diagonals are easy to determine: 1, cos(phi), cos(phi)
- off diagonal: +-sin
	- the above-right one is (-1) ^ k
![[Pasted image 20230219163705.png]]
Inverse Rotation transform: `R^(-1) = R^T`

## Composite Rotation
![[Pasted image 20230219175142.png]]
Initially, F = M, thus **Rotation Matrix** `R = I`
![[Pasted image 20230219175345.png]]
![[Pasted image 20230219175356.png]]
![[Pasted image 20230219175504.png]]
### Roll-Pitch-Yaw Transformation
![[Pasted image 20230219175554.png]]
Use rotation composition, reach an arbitrary rotation
Pay attention to the _order of multiplication_ here
![[Pasted image 20230219175730.png]]
![[Pasted image 20230219175844.png]]


# Homogeneous Coords
## Basics
Rotation can be desrcibed with 3x3 matrix. translation is a 3x1 vector
To combine these 2, add 1 dimension
![[Pasted image 20230219180236.png]]

**fundamental homogeneous translation Matrix**: Rotation matrix R = I3, movement only contains translation. Known as `tran(p)`
`inv(tran(p)) = tran(-p)`
Similarly, if there is no translation, **fundamental homogeneous rotation Matrix**:
![[Pasted image 20230219180637.png]]
Inverse:
`inv(Rot(phi,k)) = Rot(-phi,k) = transpose(Rot(phi,k))`

## Composite homogenous transformations
Note that translation also has a reletive base.
![[Pasted image 20230219203624.png]]
An example, note that 2 matrices are generated and then merged
![[Pasted image 20230219203802.png]]
To find `m1` with respect to F, its coord in F is: `T·m1 = T·transpose([1,0,0,1])`


