[[root_3D vision]]
****
# Review
## Pinhole model
world coord -- *divide z* -- normalized coord -- *calibration matrix* -- pixel coord
**in reverse**,  given pixel coord `p` and calibration matrix `A`, can recover normalised coord `m`, but **not** original coord `m_`
![[Pasted image 20230419163321.png]]

## Essential and Fundamental Matrix
Describe 2 cameras relationship. Stereo Camera or monocular camera with motion
both are 3x3, _rank == 2_
E works for calibrated cameras, 5 DOF
F for uncalibrated cameras, 7 DOF
coplanarity constraints:
`x'Fx'' == 0` `x'Ex'' == 0`, x' and x'' are a pair ofcorresponding points on different image plane.
# Pose Reconstruction
![[Pasted image 20230419164704.png]]

## Essential Matrix and 8 Points
![[Pasted image 20230419165241.png]]
8 point algo works as follows
take SVD and **set fixed values**
![[Pasted image 20230419225335.png]]
![[Pasted image 20230419225645.png]]
![[Pasted image 20230419225816.png]]

# Homography
Euclidean homography: mapping between 2 points in Eud-plains
Projective homography: mapping between 2 points in image-plain
## Euc homography matrix and 4 point algo
![[Pasted image 20230419210434.png]]
acquire relationship between `m_j` and `m_j*`
`m_j = a_j*H*m_j*`
`H = R + x/(d*)*trans(n*)`
`H`: **Euclidean Homography Matrix**
`a_j`: **Depth Ratio**
![[Pasted image 20230419212441.png]]
## SVD and Solution
![[Pasted image 20230419213009.png]]
The SVD serves as a middle bridge. Aims to recover:
- Rotation matrix `R`
- normal vector `n*`
- scaled translation `x/(d*)`
![[Pasted image 20230419213924.png]]

### Recover Procedure
first, recover the lost scale of H: `h33`
`h33 = +-sigma2`
![[Pasted image 20230419214304.png]]
3 possible scenarios:
![[Pasted image 20230419214354.png]]
![[Pasted image 20230419214404.png]]
![[Pasted image 20230419214417.png]]
`H = H_n * h33`
`a_j = 1/((trans(H3)*m_j)`
positive depth constraint: `trans(n*) * -m_j* = d* > 0`
![[Pasted image 20230419214534.png]]