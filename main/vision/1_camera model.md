[[3D vision]]
****
# basics
## Projecting to image planes
**z axis towards the image plane**
**z<-->f**
![[Pasted image 20221118225739.png]]
## Homo coord
#homo_coord add a dimision
**to convert back to physical, divide by w**
(2d physical point)
![[Pasted image 20221121013344.png]]
### line representations
![[Pasted image 20221121013523.png]]
general expression:
![[Pasted image 20221121013555.png]]
- example
- back to physical (2D) by dividing w
![[Pasted image 20221121013619.png]]

## projection matrix
to find the transformation from 3d world to 2d plains
2 considerations:
1. image center _offset_
2. _metric--pixel_ conversion
can be seen as scaling and transfering
![[Pasted image 20221121013943.png]]
==Important!!!==
#Camera_model_matrix and #Intrinsic_matrix 
camera model matrix: (3, 4)
Intrinsic matrix: (3, 3), upper triangle
==contains alpha, beta, center offset c_x, c_y==
note that #Intrinsic_matrix usually does't change
calibration is the process to determin #Intrinsic_matrix 
![[Pasted image 20221121014139.png]]
another factor: skewness
![[Pasted image 20221121014432.png]]

## world frame align
previously, the world coord and camera coord are shared
If not, **align them with rotation and translation**
![[Pasted image 20221121014632.png]]
### 3D translation
natrually, the translation can be in a 3d vector
t contains movement in 3 directions
![[Pasted image 20221121014751.png]]
note this also uses #homo_coord 
### 3D rotation
combine the rotation along 3 axis
![[Pasted image 20221121014950.png]]
![[Pasted image 20221121015031.png]]

## combination
by multiplying translation and rotation matrix (both 4x4, contains 4 parts)
![[Pasted image 20221121015234.png]]
![[Pasted image 20221121015414.png]]
#extrinsic_matrix `[R,t]`
#Intrinsic_matrix `K`
Note that #extrinsic_matrix  actually describes the camera's pose and location (位姿)
![[Pasted image 20230304220224.png]]
The projection process standardized the depth information

# calibration
![[Pasted image 20221121020015.png]]
to calibrate M, both #extrinsic_matrix  and #extrinsic_matrix 
![[Pasted image 20221121020045.png]]

# Summary
1. intrinsic matrix contains scaling and transmission factor
2. extrinsic matrix describes camera's pose and location
3. projection from 3d to 2d loses depth information. The depth is standardized to 1