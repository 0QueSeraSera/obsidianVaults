[[7 Visual Odometry 1]]
****
# Epipolar Geometry
![[Pasted image 20230307214908.png]]
## Epipolar Constrain
[[3_epipolar_geometry]]
Based on `P`, `O_1`, `O_2` being coplanar
![[Pasted image 20230307220137.png]]
![[Pasted image 20230307220152.png]]
Epipolar constrain includes #fundamental_matrix and #Essential_matrix .
With Epipolar constrain, the procedure of finding camera motion becomes:
![[Pasted image 20230307220249.png]]
Eventually, it is about **solving `R` and `t`**
We can conclude that `E` and `F` represents the same property, Their only difference is the instrinsic matrix `K`
```
E = OuterProduct(t, R)
F = trans(inv(K)) * E * inv(K)
```

## Essential Matrix and Eight-Point-Algorithm
Some properties of `E`
![[Pasted image 20230307220839.png]]
**尺度等价性**：![[Pasted image 20230307224349.png]]
![[Pasted image 20230307222214.png]]

![[Pasted image 20230307222231.png]]

![[Pasted image 20230307222246.png]]
Next, to find `R` and `t`
![[Pasted image 20230307222645.png]]


## Homography 单应矩阵
Describes feature points on the same plane
![[Pasted image 20230307223014.png]]
times addtional 1:
![[Pasted image 20230307223032.png]]
![[Pasted image 20230307223150.png]]
![[Pasted image 20230307224021.png]]


## discussion
### more matching than 8 pairs
![[Pasted image 20230307224633.png]]
![[Pasted image 20230307225850.png]]
[[RANSAC]] works as follows:
![[Pasted image 20230307225725.png]]

### Uncertainty in Scaling
![[Pasted image 20230307230125.png]]

### Pure rotation in Initialization
![[Pasted image 20230307230201.png]]