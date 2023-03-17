[[Techniques]]
[[3D vision]]
****
# Defination and Properties
## defination
2 imaginary numbers:
```
A = a + bi, C = c + di
```
define `Q = A + Cj` and `k == ij`
This yields a number in **quaternion space**:
`Q = a + bi + cj + dk` (`A + Cj`)
![[Pasted image 20230312162246.png]]
This includes real and imaginary numbers into quaternion space
![[Pasted image 20230312162528.png]]
We also define "_pure quaternions_" here:
![[Pasted image 20230312162803.png]]
Some notes:
![[Pasted image 20230312162913.png]]
### other representations
![[Pasted image 20230312163050.png]]
![[Pasted image 20230312163303.png]]

## Main Properties
### 1.Sum
![[Pasted image 20230312163342.png]]
### 2. Product
![[Pasted image 20230312163523.png]]
![[Pasted image 20230312163752.png]]
notice the matrix product equivalent
![[Pasted image 20230312164037.png]]
![[Pasted image 20230312164057.png]]

# Rotations and Cross Correlations
## 3D vector Rotation formula
Decompose a generic 3D vector rotation to its parallel and orthogonal parts.
![[Pasted image 20230312180936.png]]
With this decomposition, the parallel part remains the same.
The orthogonal part rotate with angle Phi
![[Pasted image 20230312181022.png]]
define a base in the plane where the orthogonal part rotates.
The rotation result can be represented with _parallel part_, _orthogonal part_, _rotation axis_ and _rotation angle_
![[Pasted image 20230312181045.png]]
## Rotation Group SO(3)
Rotation is linear. It preserves several important properties of the vectors.
![[Pasted image 20230312181824.png]]
Namely, the norm, the angle, and the orientation of the vectors
![[Pasted image 20230312181910.png]]
![[Pasted image 20230312181932.png]]
The formal definition of SO(3):
![[Pasted image 20230312182026.png]]
## The Rotation Group and the rotation matrix
The Rotation matrix has orthogonal condition:
`R X transpose(R) = transpose(R) X R = I`
![[Pasted image 20230312183304.png]]
This results in an additional contraint for rotation matrics:
`det(R) = 1`
![[Pasted image 20230312183352.png]]
This sort of matrices forms a subgroup of O(3), which is SO(3)
![[Pasted image 20230312183505.png]]


