[[root_3D vision]]
****
# Review
## Pinhole model
world coord -- *divide z* -- normalized coord -- *calibration matrix* -- pixel coord
**in reverse**,  given pixel coord `p` and calibration matrix `A`, can recover normalised coord `m`, but **not** original coord `m_`
![[Pasted image 20230419163321.png]]
notation: `_m: Euc coord`, `m: normalized coord`, `p: pixel coord`
## Essential and Fundamental Matrix
Describe 2 cameras relationship. Stereo Camera or monocular camera with motion
both are 3x3, _rank == 2_
E works for calibrated cameras, 5 DOF
F for uncalibrated cameras, 7 DOF
coplanarity constraints:
`x'Fx'' == 0` `x'Ex'' == 0`, x' and x'' are a pair ofcorresponding points on different image plane.
# Pose Reconstruction
notation: `_m*: camera F*`
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
previously:
![[Pasted image 20230424115255.png]]
`_m*, _m` denotes 2 camera _Euc coords_
The 2 cameras are related with a rotation and a translation
Then, `m*` and `m` denotes _normalized 2d coord_

Introduce a _normal vector_ `n*` to plane pi in camera `F*`'s frame.
`d*` is the distance from `F*` to plane
it satisfies: `d* = trans(n*) * _m*_j`
![[Pasted image 20230419210434.png]]
acquire relationship between `m_j` and `m_j*` (2 _normalized coords_)
`m_j = a_j*H*m_j*`
`H = R + x/(d*)*trans(n*)`
`H`: **Euclidean Homography Matrix**
`a_j`: **Depth Ratio**
```
H = R + trans(n*) * x / d* 
alpha_j = z_j* / z_j
```
![[Pasted image 20230419212441.png]]
## SVD and Solution
normalized `H(3,3)` to get `Hn`. `Hn(3,3) == 1`
take Hn's elements and form vector `h`
define a `M_j` matrix for jth feature. It satisfies `M_j * h = m_j`
In total, there are N feature points. Stack them up to get `M`, 2N x 8 
`Mh = m`
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

# Derivation Summary
## Acquire H
for 1 ... N pairs of features, each pair satisfies:
![[Pasted image 20230424150949.png]]
Their Euc coord is linked with a rotation `R` and a translation `x`
In frame F*, introduce a normal vector `n*` and distance `d*`
```
d* = trans(n*) * _m_j*
```
![[Pasted image 20230424151100.png]]

Combine the _distance expression_ and _Euc coord relationship_
gets a compact form:
```
m_j = alpha_j * H * m_j*
```
Still, **match feature point j in F frame with F* frame**
![[Pasted image 20230424151604.png]]
### Detail

## Solve H (reference)
normalize `H` with H33, to get `Hn`. Expand `Hn`'s free components to have vector `h = [h1, ..., h8]`
For each pair of feature points, a 2x8 `M_j` can be formed
such that `M_j * h = m_j`
Stack all N feature point pairs together, to get `M * h = m`
![[Pasted image 20230424152244.png]]
h has 8 DoF, thus at least 4 pairs are needed to make `M` larger than 8x8

`h` can be solved. This gets `Hn`
Take SVD on `Hn` (**not on H**)
`Hn = U X Sigma X V`
`Sigma = diag{sigma1, sigma2, sigma3}`
`h33 = +-sigma2` so that `det(U)det(V)sigma2 > 0`

3 scenarios:
1. all singular values are the same. **No translation, `R = H`**
2. 2 singular values are the same. **Translation is along the normal**
3. 3 singular values are all different. Motion is **General**


