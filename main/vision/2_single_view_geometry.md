[[root_3D vision]]
****
# vanishing point
vanishing point in homogeneous world frame is 0 in 4th dimension
apply **projection matrix H** to the **world homo coord** of the infinity point, ==gets a **determinanistic** coord in camera frame==
![[Pasted image 20221121225217.png]]
![[Pasted image 20221121225458.png]]
## relavance with a line
![[Pasted image 20221121225522.png]]

# measurement
### with ruler
1. determine the vanishing line with 2 vanishing points
2. place the ruler and get camera height
3. align the ruler's bottom, man's bottom, and another VP
4. align this VP and man's head and get a reading
![[Pasted image 20221121020751.png]]
### without ruler, projective invariant
==important!!!==
==cross ratio==
![[Pasted image 20221121021243.png]]
#### example
![[Pasted image 20221121021820.png]]

# ambiguity
single view can only project 3d to 2d, not reverse
