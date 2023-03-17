[[LaserSLAM]]
****
# Precondition
With known wheel odometry and laser scan data, we can:
1. construct a path completely from wheel odometry
2. Use derivatives in laser scan data to identify landmarks
3. project the found landmarks location on the map
But the path from wheel odometry becomes more and more inaccurate. The matching between perceived landmarks and real ones also drifts.
Initially, the projection is accurate
![[Pasted image 20230307160901.png]]
But as the path extends, the projection is inaccurate.
![[Pasted image 20230307161022.png]]
# Association
If we can correctly match the perceived landmarks with the real ones, this will also help the robot to locate itself
## Feature-based Localization
To utilize the landmarks (features)
The Feature-based approach
-   By extracting landmarks from the laser scan data, the computation focuses on the subset (reduces computation cost). 
-   But inaccurate when available features numbers are small
### Similarity Transform
We know the perceived matching and the real matching.
Need to find the transformation from the perceived to the real.
![[Pasted image 20230307161645.png]]
The transformation can be modelled with a _rotation_, a _translation_, and _scaling_.
Suppose the perceived landmarks' coordinates are `l_i`, the matching real ones are `r_i`
```
lambda * R * l_i + t = r_i
```
![[Pasted image 20230307162632.png]]
With error, the left side and right side aren't equal. Instead, minimize their _square error_
![[Pasted image 20230307162801.png]]


## Featureless Localization
Instead of focusing on landmarks, use the boundary information.
![[Pasted image 20230307163231.png]]
Uses **Iterative Closest Points** (ICP)
### ICP
Contains 2 steps:
- Find the point pairs
- Estimate the best transform
![[Pasted image 20230307163953.png]]
![[Pasted image 20230307164625.png]]