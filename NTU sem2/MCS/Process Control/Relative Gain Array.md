[[Chap4]]
****
# Overview
Application: input and output var have the same count
Purpose:
- Measure Process Interactions
- Recommend paring
**requires known Steady-state gains, but not the process dynamics**
# Defination
Note it is the steady state here
![[Pasted image 20230223232508.png]]
## Properties
![[Pasted image 20230223232612.png]]
1. _dimensionless_
2. **sum** of each row and column is 1
With the sum property, as a 2x2 system, 1 elements determine other 2. The other 2 are equal
#recite K11·K22 / (det())
![[Pasted image 20230223232735.png]]
# Recommend Paring
### Interaction measurement
RGA can serve as interaction measurement
![[Pasted image 20230224001349.png]]
### Recommendation rules
Corresponds to `lambda_ij` with the largest value (closest to 1)
General rules:
![[Pasted image 20230223233000.png]]
### Example
Examine by rows and columns.
Find the **Positive values** only, look for the one closest to 1
![[Pasted image 20230224002009.png]]
![[Pasted image 20230501114132.png]]
# Computation
In 2x2 system
(This formulat also follows higher order's methods)
```
lambda_11 = K11·K22 / det(K)
```

Higher Order system:
let:
```
H = transpose(inv(K))
```
`lambda_ij = K_ij · H_ij`
![[Pasted image 20230501114327.png]]

# Niederlinski Stability Theorem
![[Pasted image 20230224003254.png]]
### A general procedure
Note that `K = G(0)`
`g_ii(0)` refers to `RGA Gamma's` elements on the main diagonal line
![[Pasted image 20230224003335.png]]
### Example
![[Pasted image 20230224004428.png]]
```
After validating the previous pairing isn't stable, rearrange to this setting
```
![[Pasted image 20230224004729.png]]


# Singular Value Analysis
### Definations
SVD is calculated as follows
![[Pasted image 20230224100400.png]]

**Condition Number (CN)**:

![[Pasted image 20230224100431.png]]
### Utility
![[Pasted image 20230224100516.png]]
K is not good when CN > 10
![[Pasted image 20230224100552.png]]

### Example
Singular Value Analysis can be used to delete some I/O
![[Pasted image 20230224100905.png]]
![[Pasted image 20230224101152.png]]
