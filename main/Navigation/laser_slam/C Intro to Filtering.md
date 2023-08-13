[[topic_LaserSLAM]]
[[topic_Kalman Filter Special]]
****
# Bayes Filter
## Intro
Recall the motion scenario
![[Pasted image 20230309151916.png]]
In this scenario, the robot moves 100m, with 0.5 of chance to move exactly 100m, 0.25 to move 99m, 0.25 to move 101.
Here is the result of 2 moves
![[Pasted image 20230309152015.png]]
## Estimation and Measurement
![[Pasted image 20230309152134.png]]
motion model provides a distribution in position.
measurement of the distance to the landmarks can reflect on distance distribution as well.

**Essence**
Initially, we have a guess based on motion model `p(x)` (**Prior**)
given the real position, the measurement provides `p(z|x)`
what we want is the _corrected estimation with measurement_ `p(x|z)` (**Posterier**)

![[Pasted image 20230309152431.png]]
## Bayes Filter
![[Pasted image 20230309152740.png]]
As shown in this diagram, define:
```
belief bel(x_t) = p(x_t)
bel__(x_t+1) = p(x_t+1)
```
![[Pasted image 20230309152844.png]]
The Bayes Filter repeats this updating process:
![[Pasted image 20230309153037.png]]

# Kalman Filter
[[9 Backend1]]
## 0. Standard state and prediction formula
![[Pasted image 20230813100253.png]]
已知：k-1时刻的 _后验_ 状态估计、协方差；
k时刻的输入、观测数据
目的：k时刻的 _后验_ 状态估计
## 1. 确定x_k的*先验* (预测)
![[Pasted image 20230813100722.png]]

## 2. 贝叶斯展开x_k后验
![[Pasted image 20230813101256.png]]
![[Pasted image 20230813101602.png]]
## 3. 推导P_k
将(9.14)式的指数项展开，令x_k的一次项、二次项分别相等
二次项相等导出P_k更新式
![[Pasted image 20230813101858.png]]
## 4. 推导x_k
![[Pasted image 20230813102140.png]]
![[Pasted image 20230813102152.png]]
## 5. 总结
**预测**和**更新**
![[Pasted image 20230813102255.png]]
