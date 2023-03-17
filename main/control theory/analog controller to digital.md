[[design of the discrete control system]]
****
# overview
indirect approach
1. design in analog domain
2. obtain its digital equivalance
# general procedure
![[Pasted image 20221031223411.png]]
![[Pasted image 20221031223455.png]]

# methods for mapping G(s) to G_D(z)
==remember s and z mapping in the first 3 methods==
## backward difference
==s=(z-1)/Tz==
![[Pasted image 20221031223920.png]]
![[Pasted image 20221031224027.png]]
## forward difference
==s=(z-1)/T==
![[Pasted image 20221031224102.png]]

## bilinear transformation
https://www.youtube.com/watch?v=88tWmyBaKIQ&list=PLUMWjy5jgHK0MLv6Ksf-NHi7Ur8NRNU4Z&index=5
![[Pasted image 20221031224206.png]]
#6203_recite 
### intuitive understanding
![[Pasted image 20221101102317.png]]
Bilinear trans is an 1st order approximation of exp(sT), which is z
## pole-zero matching
#6203_recite 
==take every pole and zero in the S domain==
==and move them to Z domain==
==**z = exp(sT)**==
https://www.youtube.com/watch?v=TPNiLqsdwNI&list=PLUMWjy5jgHK0MLv6Ksf-NHi7Ur8NRNU4Z&index=4
![[Pasted image 20221031225943.png]]
in step 2, the additional zeros count equals to:
`num of finite poles - num of finite zeros - 1`
with `-1`, step 3 is included
step 4, calculate DC gain alpha with:
`G_D(z)|z=1 = G(s)|s=0`
![[Pasted image 20221031230815.png]]
### example
![[Pasted image 20221105113354.png]]
![[Pasted image 20221105164803.png]]

## summary and memorizaiton
backward: s = (z-1)/Tz
forward: s = (z-1)/T
	_backward is one **z** more in the D, thus dragging it back_
bilinear:
bi, thus has z and 1 in both N and D
s = (2/T) · (z-1)/(z+1)
	-1 is smaller than 1, compensate with 2 and T respectively
	**(z-1) as N is universal**
pole-zero matching
#6203_recite 
_(z+1)^(n-m-1) here is unique_
**(z+1), not (z-1)**
_directly convert roots in S to Z with s = exp(sT)_
![[Pasted image 20221106104821.png]]
![[Pasted image 20221106104830.png]]
s-pole --> z-poles; s-zeros --> z-zeros
key: ==s-->exp(sT)==
z=exp(sT), s = 1/T * ln(z)
