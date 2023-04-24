[[2. Kinematics]]
****
# Link Coordination
Goal: systemically assign coordinate frames to links
Acquiring a general motion equation
## Kinematics parameters
link k and link k-1 are connected by joint k.
Use 2 _joint parameters_ to specify relative position and orientation.
- **joint angle** `theta_k`: angle between axis x_k and x_k-1 about z_k-1
- **joint distance** `d_k`
![[Pasted image 20230221205641.png]]
![[Pasted image 20230221205811.png]]

Just like the _joint parameter_ describing the successive 2 links
there is _link parameter_ to describe 2 successive joints
- link length
- link twist angle
Note that _link parameters_ are fixed
![[Pasted image 20230221210131.png]]

## Normal, Sliding and Approach vectors
Orientation of the tool
![[Pasted image 20230221210346.png]]
These 3 vectors have specified directions
![[Pasted image 20230221210451.png]]






