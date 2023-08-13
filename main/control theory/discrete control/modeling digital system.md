[[topic_discrete_control]]
****
# Impulse Sampling and Data Hold
## ADC model
- continuous signal --> train of impules
with a impulse sampler, x(t) --> x*(t)
X(s) --> X*(s)
can prove that by letting
`s = 1/T*ln(z)`
==X*(s) --> X(z)==
## DAC model
- train of impules --> continuous signal
### Zero-order hold
![[Pasted image 20221031160757.png]]
![[Pasted image 20221031160850.png]]
### First-order hold

# Pulse Transfer Function
- equivalant to transfer function in CT
- **G(z) = Y(z) / X(z)**

## obtaining the PTF
==**without** a input sample, **cannot** get G(z) via Z-transforming G(s)==
while the output sampler does not affect
### DAC and analog system
![[Pasted image 20221103162546.png]]
X(s) = G(s) * (1 - exp(-Ts)) / s
==X(z) = (1 - 1/z) * Z{X(s)/s}==
**note: this is often used in [[design of the discrete control system]]**
### cascade controller
similarly, 
![[Pasted image 20221031163926.png]]
	(a) G(z) = X(z)/Y(z) = X*(s)/Y*(s) = G(z)H(z)
	(b) G(z) = X(z)/Y(z) = X*(s)/Y*(s) = ==Z{G(s)H(s)} != G(z)H(z)==

### close-loop system
**practical cases**
seperate C(z) and R(z)
![[Pasted image 20221126163732.png]]
PTF: C(z)/R(z) = G(z)/(1+GH(z))
some exceptions ...

[[close-loop digital controller]]
