[[topic_Visual_SLAM]]
****
#VO is divided into feature points method and optical flow method
# Recap on camera model
## Matrices
3 Matrices: #extrinsic_matrix #Intrinsic_matrix #projection_matrix

intrinsic matrix describes inner config of the camera, like sensor size, focal length, lens distortion etc. It is **3X3**. *It converts the 3D coord in camera's coordinate system to 2D coords of the image plane.*

extrinsic matrix describes the camera's position and orientation relative to the global frame. It is **4X4**, *combines* a _3X3 rotation matrix_ and a _3X1 translation vector_

Projection matrix, or camera matrix
![[Pasted image 20230310191318.png]]
Note that it is **not** the product of intrinsic and extrinsic matrix even the dimension is matched
## Coordinates
![[Pasted image 20230310191512.png]]
![[Pasted image 20230310191938.png]]
![[Pasted image 20230310192003.png]]

# Feature Points
![[Pasted image 20230305162056.png]]
Feature point consists of **Key-point** and **Descriptor**. Key-point describes positioning info of the feature points in the image. Descriptor is a vector

# ORB Feature
![[Pasted image 20230305162435.png]]
Key-point: Oriented FAST
Descriptor: BRIEF
## Fast Key-point
Famous for being rapid. Only computes on brightness
![[Pasted image 20230305162732.png]]
Drawbacks:
- distribution is not unified
- cannot easily be repeated
- the detection circle cannot cope with different scaling images
- doesn't contain direction info
![[Pasted image 20230305163110.png]]
_image pyramid_ and _Intensity Centroid_



## BRIEF Descriptor


# Feature Matching
![[Pasted image 20230307225132.png]]
![[Pasted image 20230307225146.png]]
![[Pasted image 20230307225450.png]]

# Camera Movement
![[Pasted image 20230307214350.png]]
[[2D-2D solution]]

