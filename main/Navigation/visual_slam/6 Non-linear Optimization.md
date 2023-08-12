[[topic_Visual_SLAM]]
****
# Review
1. Slam consists of 1 _state_ formula, and 1 _observation_ formula
![[Pasted image 20230812155842.png]]
2. Essence of estimation: **given observation， derive the state**
![[Pasted image 20230812160115.png]]
3. Bayes Rule and MLE
![[Pasted image 20230812160206.png]]
待求的是**后验**概率，根据贝叶斯转换为**先验乘以似然**
最大似然估计MLE：忽略先验：
![[Pasted image 20230812160445.png]]
## recall MAP
a reminder of MAP [[topic_Bayes Theory]]
![[Pasted image 20221122023159.png]]
think of a classification problem with given observation x, the classification is `P(omega|x)`
```
P(omega|x) = P(x|omega) · P(omega)
```
## MLE
![[Pasted image 20230305154340.png]]
![[Pasted image 20230305154617.png]]
## Comparison
```
MAP: argmax{P(x,y|z,u)} = argmax{P(z,u|x,y)P(x,y)}
MLE: argmax{P(z,u|x,y)}
```

# 最小二乘
## An example scenario
`y = Hx` has no solution, but we can aim to find a x that is "**closest**" to y （最小二乘拟合）
## SLAM scenario
Observation z follows a Gaussian distribution
![[Pasted image 20230812173139.png]]
由负对数展开高斯分布表达式，可以得到：
![[Pasted image 20230812173436.png]]
求x,y 分布，由贝叶斯转换到极大似然，高斯的噪声可以进一步用LS求解
![[Pasted image 20230812173545.png]]
![[Pasted image 20230812173629.png]]
## A SLAM example
![[Pasted image 20230812173727.png]]
![[Pasted image 20230812173812.png]]
![[Pasted image 20230812173917.png]]
![[Pasted image 20230812173934.png]]
![[Pasted image 20230812174016.png]]
# Non-linear LS
在最小二乘中，希望最小化目标函数。有时可以通过最目标函数求导得到极值，若不能，则使用迭代方式
![[Pasted image 20230812174723.png]]
## 一阶与二阶梯度法
在`x_k`处使用**泰勒展开**
![[Pasted image 20230812174831.png]]
牛顿法
![[Pasted image 20230812174846.png]]
总结：
![[Pasted image 20230812174943.png]]
## 高斯牛顿法
核心：
- 用Jacobian的乘积近似Hessian
- 理解为最小二乘问题，目标是最小化残差平方和
![[Pasted image 20230812181417.png]]
![[Pasted image 20230812181426.png]]
![[Pasted image 20230812181450.png]]
步骤：
![[Pasted image 20230812181530.png]]

## 列文伯格-马夸尔特
![[Pasted image 20230812181844.png]]
引入信赖区域后，流程：
![[Pasted image 20230812182002.png]]


