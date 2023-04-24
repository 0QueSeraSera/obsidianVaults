[[topic_Bayes Theory]]
****
# multi-variable and loss function
the #loss_function  states exactly how costly each action is, and is used to convert a probability determination into a decision
![[Pasted image 20221120225939.png]]
loss function:
#loss_function : lambda(alpha_i|omega_j)
#conditional_risk :R(alpha_i|x)
![[Pasted image 20221120230143.png]]
![[Pasted image 20221120230246.png]]
#decision_rule based on #conditional_risk : #bayes_decision_rule  minimize the overall risk, compute #conditional_risk 
#conditional_risk : 
	==sum over all classes, #posterior X #loss_function ==
![[Pasted image 20221120232237.png]]

# Two-catagories classification
![[Pasted image 20221120233044.png]]
![[Pasted image 20221120233223.png]]
#Likelihood_Ratio_Test #decision_rule 
## MAP Rule
![[Pasted image 20221120233318.png]]
#MAP_rule is the 0/1 loss function case of bayes rule 
#MAP_rule minimizes the error rate
#decision_rule 
Transform #conditional_risk :
![[Pasted image 20221120233549.png]]
![[Pasted image 20221120234206.png]]

# Multi-catagories case
## descriminant function
#descriminant_function 
![[Pasted image 20221121144444.png]]
wrong categories' #descriminant_function  has smaller values than the correct one
![[Pasted image 20221121144510.png]]
## multi-variable gaussian
![[Pasted image 20221121145237.png]]
#descriminant_function is a **quadradic** function of x:
![[Pasted image 20221121145328.png]]
#mahalanolobis_distance
![[Pasted image 20221121145417.png]]

## quadradic classifier
quadradic refers to decision surfaces being hyperquadrics
**the decision boundary is obtained by setting ===g_i(x) = g_j(x)===**

**important!!!**:
remember the form of #descriminant_function g of the gaussian 