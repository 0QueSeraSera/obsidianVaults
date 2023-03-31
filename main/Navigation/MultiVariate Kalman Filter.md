[[topic_LaserSLAM]]
[[topic_Kalman Filter Special]]
****
# Overview
A general procedure of the Bayesian Filter and its variances:
![[Pasted image 20230310145228.png]]
Key factors: 
- **state variables**: specify what is the observed data
- **process model**: to predict the future states
- **measurement**: to measure the state variables
What a filter does:
Compute a Gain to add up _weighted_ measurement and prediction
# Representation
![[Pasted image 20230310145600.png]]
Note that different from #state_space_model , the filter also **updates states' covariances**
![[Pasted image 20230310145911.png]]
The final estimation that blends _measurement_ and _prediction_ is the same form:
```
x = x_pred + K · (x_measure - x_pred)
```
![[Pasted image 20230310145935.png]]
## Estimation of Q
