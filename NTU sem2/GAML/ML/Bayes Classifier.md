# Bayes Decision Theory
![[Pasted image 20230423171804.png]]
## Generalization
Extend the case from 2-class, single feature to multiple features and multiple classes.
![[Pasted image 20230423171838.png]]
## Classifier Design
Systematically designed with the *descriminant function*
![[Pasted image 20230423172006.png]]
![[Pasted image 20230423172018.png]]

# Parameter Estimation for Gaussian
## Gaussian Model
![[Pasted image 20230423172153.png]]
Note, the density function meets: `int{px}(-inf, inf) == 1`
`P(x)<=a == int{px}(-inf, a)`
![[Pasted image 20230423173856.png]]
## Maximum Likelihood 
The **likelihood** of a parameter `theta` with sample set `D`, is acquired by **Multiplying each sample's probability**
![[Pasted image 20230423174410.png]]
MLE estimated the `theta` that maximizes **Likelihood**
![[Pasted image 20230423174615.png]]
![[Pasted image 20230423174649.png]]
### Unknown mu
![[Pasted image 20230423174849.png]]
![[Pasted image 20230423174857.png]]

### Unkmown mu and sigma
`mu`'s expression is the same.
`sigma`' the mean of square error r.w.t. estimated `mu`
![[Pasted image 20230423174928.png]]




# GMM
![[Pasted image 20230423175451.png]]
![[Pasted image 20230423175557.png]]

## Param Estimation
Introduce a variable: P of `x` belongs to Gaussian Component `o_i`
![[Pasted image 20230423175907.png]]
Can still use MLE. Unlike Bayes decision rule, here the denominator cannot be overlooked.
![[Pasted image 20230423175745.png]]
However, the derivatives are nested, use **EM: Expectation Maximization** instead
![[Pasted image 20230423180153.png]]
### EM Method
![[Pasted image 20230423193719.png]]
![[Pasted image 20230423193749.png]]
![[Pasted image 20230423193811.png]]