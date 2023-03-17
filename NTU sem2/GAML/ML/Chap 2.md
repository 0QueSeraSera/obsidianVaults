# Linear Descriminant Analysis (LDA)
A classification tool
Use a hyperplane to seperate samples
## Overview
The **descriminant fundtion**, denoted as g:
```
g(x) = trans(w) X x + w_0
```
![[Pasted image 20230316173142.png]]
`w` is the coefficient, known as weight vector.
The decision rule is based on g(x) being positive or negative
## Property
The hyperplane of `g = 0`, its weight vector `w` is **normal** to it
![[Pasted image 20230316173413.png]]

`g(x)` itself represents the _distance_ of x to the `g(x)=0 plane`

![[Pasted image 20230316173520.png]]

One illustration as follow:
a few discoveries:
1. `w` is normal to plane `H: g(x)=0`
2. distance `r`, `r = x - x_p`
3. `r = g(x) / ||w||`
4. H's distance to the origin: `w0 / ||w||`
![[Pasted image 20230316173659.png]]

![[Pasted image 20230316173729.png]]

# Fisher's LDA
Fisher's LDA aims to find a hyperplane that `maximizes the seperation between classes`  _while_ `minimizes the variance within each class`
![[Pasted image 20230316180426.png]]
## Math
use the `mean` to analyze
![[Pasted image 20230316180456.png]]
The distance between projected mean:
![[Pasted image 20230316180811.png]]

Define the scatter of data _within each class_
![[Pasted image 20230316180852.png]]
Totally within-class scatter:
![[Pasted image 20230316180918.png]]

The key criteria: 
`distance between classes` divided by `scatter within each class`
![[Pasted image 20230316180940.png]]
Define the `explicit function` and 2 matrices: `S_w`, `S_B`
We have the simplication:
![[Pasted image 20230316181718.png]]
### detail of simplification
![[Pasted image 20230316181456.png]]
![[Pasted image 20230316181618.png]]
![[Pasted image 20230316181632.png]]



### Rayleigh quotient
With constraints, the problem can be solved with eigenvalues:
![[Pasted image 20230316181958.png]]

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
![[Pasted image 20230316183047.png]]
![[Pasted image 20230316183058.png]]



# Multiple LDA
