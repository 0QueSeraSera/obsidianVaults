[[Bayes Theory]]
****
# background
designing a classifier to separate two kinds of fish: sea bass and salmon
## state of nature
state_of_nature ![[Pasted image 20221120220700.png]]
**==goal is to decide the state_of_nature ==**

## priori
omega_j
#priori P(omega_j)
sum(P(omega_j)) = 1

## decision rule
#decision_rule
![[Pasted image 20221120220909.png]]
#MAP_rule 
maximum a #posterior 
omega_k = argmax(p(omega_i|x))
![[Pasted image 20221122023159.png]]
## class-conditional probabilities density
#class_conditional_probability ![[Pasted image 20221120221121.png]]
compare this two figures:
the first one is each state_of_nature 's distribution of x. state_of_nature omega_j is given, thus it is p(x|omega)
the second is #posterior ,given observed x, the probability that the category is omega_j
![[Pasted image 20221120221224.png]]
![[Pasted image 20221120222300.png]]
## Bayes formula

`review note on 2023.3.36`
`x` is the observed data, `omega_j` is the class. we have observation data `x`, want to decide class based on observation. Thus, the desired probability is `P(omega_j|x)` 
Use bayes formula, it is _proportional_ to `P(x|omega_j)` and `P(omega_j)`. These 2 are easy to acquire. 
`P(x|omega_j)` is called **likelihood**, 
`P(omega_j)` is **prior**, 
and the desired `P(x|omega_j)` is **posterior**


![[Pasted image 20221120221501.png]]
#posterior is what we want: 
==given observation data x, decide catogory omega==
![[Pasted image 20221120221738.png]]
the key factor is #likelihood X #priori 

## probability of error
![[Pasted image 20221120221925.png]]
this is when x is observed, a wrong decision is made
**==Thus, it is conditioned on x==**
![[Pasted image 20221120223214.png]]
![[Pasted image 20221120223246.png]]

## decision rule
#decision_rule 
![[Pasted image 20221120222855.png]]
![[Pasted image 20221120222934.png]]
(8) integrates bayes formula

