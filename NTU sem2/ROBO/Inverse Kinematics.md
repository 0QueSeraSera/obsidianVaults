# Overview
To find the mapping from `tool-configuration space` to `joint space`
![[Pasted image 20230219141216.png]]
## Tool Configuration
![[Pasted image 20230219141451.png]]
Rotation matrix has redundant information
A new method for description: **approach vector**
As mentioned in[[Link Coordination]], approach vertor aligns with the tool's roll axis, to the tool's **pointing direction** 
Thus, it specifies _direction only_
We need to derive the roll angle `q_n` from the scaled approach vector
![[Pasted image 20230219141630.png]]
**Tool-Configuration Vector** r6, 3 elements denotes position and the other 3 describe rotation

![[Pasted image 20230219141748.png]]
### Additional Explaination
![[Pasted image 20230219160253.png]]
#todo the relationship between rotation angle and r3 vector
In the **arm equation**, the last column in the `R(q)` submatrix is the *approach vector*
The approach vector aligns with the tool's roll axis, thus it can not represent roll value alone
![[Pasted image 20230221232021.png]]
We utilize the **scaling** of the approach vector
Combining the roll angle's info with the approach vector
![[Pasted image 20230221232605.png]]

# Inverse Kinematics
**Numerical** methods and **analytical** methods
![[Pasted image 20230219160544.png]]
![[Pasted image 20230219160614.png]]
## Existance and Uniqueness of the solution
### Existance
- tip position must be in the work envelop
- orientation must be realizable
- Unknown variables count
- ![[Pasted image 20230222114559.png]]
### Uniqueness
typically not unique
## Example: 
### 1. 5-axes robot
**tool configuration vector**
![[Pasted image 20230222114825.png]]




