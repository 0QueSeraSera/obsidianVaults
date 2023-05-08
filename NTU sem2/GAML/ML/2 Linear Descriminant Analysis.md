# Linear Discriminant Analysis (LDA)
A classification tool
_Use a hyperplane to separate samples_
## Overview
The **discriminant function**, denoted as g:
```
g(x) = trans(w) X x + w_0
```
![[Pasted image 20230316173142.png]]
`w` is the coefficient, known as weight vector.
The decision rule is based on g(x) being positive or negative
## Property
The hyperplane of `g = 0`, its weight vector `w` is **normal** to it
![[Pasted image 20230316173413.png]]

`g(x) = trans(w)x + w_0` itself represents the _distance_ of x to the `g(x)=0 plane`

![[Pasted image 20230316173520.png]]

One illustration as follow:
a few discoveries:
1. `w` is normal to plane `H: g(x)=0`
2. distance `r`, `r = x - x_p`
3. `r = g(x) / ||w||`
4. H's distance to the origin: `w0 / ||w||`
![[Pasted image 20230316173659.png]]

![[Pasted image 20230316173729.png]]

# Fisher's LDA: A criterion
Fisher's LDA aims to find a hyperplane that `maximizes the seperation between classes`  _while_ `minimizes the variance within each class`

**utilize the property of projection on w**
**find the w that projection is separated well**
![[Pasted image 20230316180426.png]]
## Math
### formulation
use the `mean` to analyze
First, acquire the samples' mean.
Then, acquire the _projected_ samples' mean
`~m = trans(w) * m_i`
![[Pasted image 20230316180456.png]]
The _distance_ between projected mean:
![[Pasted image 20230316180811.png]]

Define the **scatter** of data _within each class_. A measurement about how scattered samples are within a class.
`class i: (~s)^2 = sum{[g(x) - ~m]^2}`
![[Pasted image 20230424163112.png]]
![[Pasted image 20230326212853.png]]

**Totally within-class scatter**:
![[Pasted image 20230316180918.png]]

The key criteria: 
Maximize:
`distance between classes` divided by `scatter within each class`
![[Pasted image 20230316180940.png]]
Define the `explicit function` and 2 matrices: `S_w`, `S_B`
`S_b` is the _between-class scatter matrix_
`S_w` is _within-class scatter_
We have the simplication:
![[Pasted image 20230316181718.png]]
### detail of simplification
![[Pasted image 20230316181456.png]]
![[Pasted image 20230316181618.png]]
![[Pasted image 20230316181632.png]]



### Rayleigh quotient
To solve for the `w`, reach out to eigenvalue solution
With constraints, the problem can be solved with eigenvalues:
![[Pasted image 20230326214011.png]]
`inv(S_W) X S_B X w = lambda * w` forms a _eigenvalue_ problem. And w is the eigen vector of `inv(S_W) X S_B`

### Solution without eigenvalue
Define the difference of sample mean projection
![[Pasted image 20230316182644.png]]
Substitute `S_B`
![[Pasted image 20230316182727.png]]
![[Pasted image 20230316182837.png]]
Above solves the weight vector `w`
The bias `w_0` can be solved with:
![[Pasted image 20230316182914.png]]
### Solution with eigenvalue
![[Pasted image 20230316183209.png]]

## Summary
Note: This part contains how to classify a 2-class problem **after getting w**

note the calculation of `w_0`
![[Pasted image 20230316183047.png]]
![[Pasted image 20230316183058.png]]



# Multiple LDA
## generalization
The required number of descriminant function and data's dimision change
for a c-class problem, there is c-1 descriminant functions
**Within-class scatter matrix** are the same
![[Pasted image 20230424202920.png]]

Introduce **total mean** and **total scatter** matrix
![[Pasted image 20230424203128.png]]
note `S_T = S_W + S_B`
with `S_B` being the weighted sum of of each classes' **difference**
Note that `S_W` and `S_T` do _not divide sample_num_, the same with 2-class case.
![[Pasted image 20230424203208.png]]

Now we can form c-1 **discriminant functions**
![[Pasted image 20230424203638.png]]
![[Pasted image 20230424203853.png]]
