![[Pasted image 20230424211012.png]]
#concept ![[Pasted image 20230424211106.png]]
## node impurity measurement
### 1. Entropy impurity
![[Pasted image 20230424211250.png]]
![[Pasted image 20230424211320.png]]

### 2. Variance and Gini impurity
**variance impurity** -- more classes --> **Gini impurity**
![[Pasted image 20230424211613.png]]
### 3. Misclassification Impurity
Take the _largest proportion_. The higher it is, the more pure it is.

![[Pasted image 20230424211751.png]]

## Query Selction
Select the one that brings the largest drop
![[Pasted image 20230424212240.png]]
For multiple branches, it may favour large branch number
![[Pasted image 20230424212504.png]]
Scale the expression #concept `gain ratio`
![[Pasted image 20230424212647.png]]

## When to stop splitting
![[Pasted image 20230424213348.png]]
