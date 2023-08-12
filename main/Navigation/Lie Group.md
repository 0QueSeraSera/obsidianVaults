[[topic_Visual_SLAM]]
****
https://zhuanlan.zhihu.com/p/358455662
# Intro concepts
## 正交特殊群SO3
- ![[Pasted image 20230812112207.png]]
example: rotation matrix
## 特殊欧氏群 SE3
![[Pasted image 20230812112312.png]]
example: 变换矩阵，Transform matrix
## 旋转向量
目的：更紧凑地表示旋转
![[Pasted image 20230812112404.png]]
# Lie Group
## An optimization problem
Use **Iteration**
![[Pasted image 20230812112602.png]]
![[Pasted image 20230812112706.png]]
SO(3) cannot use **adding**
Use Lie group to apply adding

## Group definition
**A union** + **A calculation**
![[Pasted image 20230812112811.png]]
## Lie Group
_Continuous_
![[Pasted image 20230812112915.png]]
![[Pasted image 20230812113001.png]]
