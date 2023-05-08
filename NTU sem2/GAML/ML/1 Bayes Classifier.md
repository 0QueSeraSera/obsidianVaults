# Bayes Decision Theory
![[Pasted image 20230423171804.png]]
## Generalization
Extend the case from 2-class, single feature to multiple features and multiple classes.
![[Pasted image 20230423171838.png]]
## Classifier Design
Systematically designed with the *descriminant function*
![[Pasted image 20230423172006.png]]
![[Pasted image 20230423172018.png]]
## 2D Gaussian Example
![[Pasted image 20230424155400.png]]
#recite 
`mu = sum{all samples in the class} / sample_num`
`Sigma = sum{(x-mu)*trans(x-mu)} / sample_num`
![[Pasted image 20230424155740.png]]
specify the _class-conditional P_
![[Pasted image 20230424160111.png]]
Specify the _discriminant function_
`g_i(x) = p(x|w_i)p(w_i)`
Note that, set `x` as the to-be-classified sample directly
![[Pasted image 20230424160132.png]]
Lastly, specify the terms
![[Pasted image 20230424160347.png]]
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
denote `gamma_i(x) = P(o_i|x)`. Try to make 0 derivatives with its log form.

However, the derivatives are nested, use **EM: Expectation Maximization** instead
![[Pasted image 20230423180153.png]]
## EM Method
![[Pasted image 20230423193719.png]]
1. random initialization at _j=0_
2. increment j. Estimate `gamma` based on previous 3 derivatives values
3. Update 3 derivatives value with new 
4. `gamma`
![[Pasted image 20230423193749.png]]
![[Pasted image 20230423193811.png]]

## Example
![[Pasted image 20230424200350.png]]
![[Pasted image 20230424200432.png]]
![[Pasted image 20230424200448.png]]
![[Pasted image 20230424200554.png]]