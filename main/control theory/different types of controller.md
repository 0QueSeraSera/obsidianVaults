[[design of the discrete control system]]
****
# 1 DOF feedback controller
![[Pasted image 20221125200230.png]]
includes another input v
seperate the v and r's effect
![[Pasted image 20221125200335.png]]
goal:
1. make y(n) follow r(n)
2. remove the effect of v(n) on y(n)
subject to
`S(z) + T(z) = 1`
# 2 DOF
![[Pasted image 20221125200515.png]]
![[Pasted image 20221125200635.png]]
Rc, Sc, Tc are polynomials in z^-1
u = r · Gf - y · Gb
# Pole-placement controller
## setup
**attention**:
1. G is in this form:`z^(-k) · B/A`
2. feedforward has Tc and Gamma, Feedback has Sc
![[Pasted image 20221127124132.png]]
## Goal:
follow input signal r:
![[Pasted image 20221127124320.png]]
Phi_cl is the close-loop characteristic polynomial
gamma is determined with:
![[Pasted image 20221127124442.png]]
## derivation **(focus on 5.19)**
U(z) = R(z) · feedforward - y · feedback
reorganize the denominator:
![[Pasted image 20221127124502.png]]
![[Pasted image 20221127124609.png]]
with 5.18, sub into:
![[Pasted image 20221127124651.png]]
### details:

we have:
![[Pasted image 20221127124707.png]]
This is the y's expression, **let it be equal with the desired y 5.18:**
![[Pasted image 20221127124812.png]]
decompose B, A as good and bad factors
and let Rc, Sc, Tc be:
![[Pasted image 20221127124913.png]]
with this, 5.19 becomes:
![[Pasted image 20221127124952.png]]
seperately, equate Numerator and Demominator,
**to solve R1 and S1**

![[Pasted image 20221127125029.png]]
we can set `T1 = 1`
![[Pasted image 20221127125128.png]]
## example

![[Pasted image 20221127125359.png]]
#### step1 turn to `G(z) = z^(-k) · A/B`
![[Pasted image 20221127125452.png]]
#### step2 seperate good and bad factors
good: stable poles or zeros
bad: unstable ones
![[Pasted image 20221127125523.png]]
#### step3 accquire Phi_cl
Phi_cl is given by specifications (setttling time etc.)
![[Pasted image 20221127130003.png]]
#### Step4 solve s1, r1 **important**
**use 5.22, denominator equation**
![[Pasted image 20221127125029.png]]
![[Pasted image 20221127130206.png]]
we get:
![[Pasted image 20221127130220.png]]
#### step5 obtain Sc, Rc, Tc **important**
**use 5.20**
![[Pasted image 20221127130328.png]]
![[Pasted image 20221127130348.png]]


