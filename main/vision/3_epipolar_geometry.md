[[3D vision]]
****
# base
![[Pasted image 20221121022105.png]]
==goal: find the epipolar line given camera params==


## known in/ex matrix
![[Pasted image 20221121022540.png]]
### coplanar constrain
![[Pasted image 20221121022737.png]]
#Essential_matrix 
![[Pasted image 20221121023048.png]]
### computation
![[Pasted image 20221121023202.png]]

## unknown Ex mtx
![[Pasted image 20221121023323.png]]
#fundamental_matrix 
![[Pasted image 20221121023353.png]]
computation:
![[Pasted image 20221121023441.png]]
### estimating F
8-point algorithm

## special case: parallel image planes
![[Pasted image 20221121023703.png]]
### image rectification
![[Pasted image 20221121023801.png]]

