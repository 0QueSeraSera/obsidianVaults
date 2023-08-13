[[topic_discrete_control]]
[[topic_classical control]]
****
# 1. Intro & 2. basics
for continuous signal x(t):
`X(z) = Z[x(t)] = sum(k=0->inf)[x(kT)z^-k]`
for sequence signal x(k):
`X(z) = Z[x(k)] = sum(k=0->inf)[x(k)z^-k]`

# 3. elementary Z-t functions

# 4. theorems
## Shifting
![[Pasted image 20221031131509.png]]
**note: 
1/z <==> delay one unit <==> shift ==right==
z<==> advance 1 unit<==>  shift ==left** ==

## Initial and Final Value
they both talk about x‘s value, initial at x(0), final at x(inf)
these two are related to other direction of X(z), X(z)|z=inf and X(z)|z=1, but actually (1-1/z)X(z)|z=1
![[Pasted image 20221031131827.png]]
![[Pasted image 20221125161618.png]]
#6203_recite 
```
lim{k->inf}x(k) = lim{z->1}(1-1/z)X(z)
```
#final_value_theorem  exception cases:
![[Pasted image 20221126170841.png]]
to use initial value theorem, X(z)|z=inf must exist
# 5. Inverse Z-transform
## * direct division (long division)
convert X(z) to series of z^-1
==by Z-transform definition==

First, write X(z) in forms of 1/z
![[Pasted image 20221031132517.png]]


## partial fraction expansion
write the denominator in multiplications of poles:
![[Pasted image 20221031133000.png]]
==**divide X(z) by z**, seperate the right side:==
![[Pasted image 20221031133216.png]]
refer to transform table, accquire **pole's exponentials**
![[Pasted image 20221031133414.png]]
## inversion integral
#6203_recite 
```
x(k) = sum over Ki
Ki = lim{z->zi}[(z-zi)X(z)z^(k-1)]
```
![[Pasted image 20221126004943.png]]

# 6. Solve difference equations
![[Pasted image 20221031134233.png]]
