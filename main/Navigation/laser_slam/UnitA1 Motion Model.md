[[topic_LaserSLAM]]
[[kinematics]]
****
# motion modelling
## differentiate drive model
**known w, l, r ==> alpha, R**
![[Pasted image 20221205160640.png]]
```
l = alpha · R
r = alpha · (R+w)

l - r = alpha · w
```
we have:
	`alpha = (r-l)/w`
	`R = l/alpha`

## integrate to world coord
Given: 
	original position and heading: (x, y, theta)
	movement: (l, r)
	width: w
![[Pasted image 20221205161558.png]]
derive new position and heading: `(x', y', theta')`
define the original heading with theta

derive the new position is _P'_
```
P' = C + (R+ w/2) · 
	[sin(theta + alpha), -cos(theta + alpha)]^T
```
![[Pasted image 20221205162057.png]]

