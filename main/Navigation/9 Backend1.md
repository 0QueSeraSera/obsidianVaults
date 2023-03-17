[[Visual_SLAM]]
****
# Recap
1. VO only has "short memory". As time goes on, the error accumulates
2. Batch optimization can be viewed as an #MAP problem solved with #MLE 

# Probability Description of States
![[Pasted image 20230305225154.png]]
with noise in observation and motion equation, `x` and `y` are random variables
**with motion data `u` and observation data `z`, how to determine x, y's distribution**
![[Pasted image 20230305225330.png]]

Redefine `x_k` and `z_k`:
`y` is integrated with `x`
![[Pasted image 20230305225852.png]]
