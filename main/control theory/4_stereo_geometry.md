# depth from disparity
z = fB/d
![[Pasted image 20221122110041.png]]
![[Pasted image 20221122110029.png]]
d contains error delta_d:
![[Pasted image 20221122110118.png]]
delta_z is calculated by ==different d and d + delta_d==
#Taylor_expansion at 0:
![[Pasted image 20221122110313.png]]

# correspondence search
where is the corresponding point on the other image?
![[Pasted image 20221122110625.png]]
taking the window
![[Pasted image 20221122110707.png]]
constraints:
![[Pasted image 20221122110833.png]]
