[[topic_Visual_SLAM]]
****
2 types of optimization:
- incremental: given a current estimate, update it with new observations
- batch: save up some data and compute it altogether

# Batch
![[Pasted image 20230305153546.png]]
![[Pasted image 20230305154022.png]]
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
