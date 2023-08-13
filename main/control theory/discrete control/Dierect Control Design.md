[[design of the discrete control system]]
****
# important formula:
## 5.11: **general close loop cases, connects C, G_cl, G_zAS** 
C(z) = 1/G_cl(z) * G_cl(z)/(1-G_cl(z))
![[Pasted image 20221107114857.png]]
	connects C, G_cl
## 5.12: **deadbeat controller, with G_cl = z^(-k)** 
![[Pasted image 20221107114210.png]]

## 5.13: U(z)'s properties (steady in n steps) is given, determine G_cl by this
==cancel out unwanted denomenators==
![[Pasted image 20221107195620.png]]
if the deadbeat requirement is on E(z), E(z) = U(z)/C(z),
C(z) must have a integrator, 
assume C(z):
![[Pasted image 20221107200829.png]]
**lastly, it is still about design a G_cl to cancel denomenators**
**and apply 5.11 to gain C(z)**

## 5.13 ripple-free case, determine U(z)
![[Pasted image 20221107122914.png]]
core of ripple-free controller
# setup
- desired **close-loop transfer function** is known
- calculate the controller's transfer function from close-loop tf
close-loop tf:
```
G_cl(z) = Y(z)/R(z)
	Y(z) = (R(z)-Y(z))C(z)G_zas(z)
Y(z)/R(z) = (1-Y(z)/R(z))C(z)G_zas(z)
G_cl(z) = C·G_zas/(1+C·G_zas)
```
with this, derive C(z)
#6203_recite 
`C(z) = G_cl/((1-G_cl)G_zas)`
![[Pasted image 20221103152454.png]]
## conditions
the **controller** must be causal, and ensures asymptotic stability
### 1_causal
- no time advance
- poles no less than zeros
### 2_asymptotic stability
zeros of G_cl(z) must include all **outside-unit-circle** zeros of G_ZAS(z)
zeros of `1-G_cl(z)` must include all **unstable poles** of G_ZAS(z)
### summary
_note: these four can be memorized as cancellation needs_
```
(1/G_zas) · (G_cl/(1-G_cl))
use G_cl and 1-G_cl to cancel out all the unstable poles and zeros of G_zas:
G_cl <--> N_zas <--> G_zas`s zeros
1-G_cl <--> D_zas <--> G_zas`s poles
```
1. relative degree
2. cover unstable zeros
3. 1-G_cl(z) covers poles
4. steady-state error
![[Pasted image 20221103153621.png]]
G_cl(1) = 1 due to final value theorem
#final_value_theorem 
# procedure for choosing G_cl(z) **a general scenario, do not ignore**
![[Pasted image 20221103153724.png]]
## example1
![[Pasted image 20221103153923.png]]
obtain `G_zAS(z) = (1-1/z)·Z{G(s)/s}`
	analysis:
		G_zAS does not have unstable _poles_ or _zeros_
		_relative degree_ of 1
![[Pasted image 20221103165736.png]]
1. [[modeling digital system]] DAC & analog part
	**important**
	#6203_recite 
	`X(z) = (1 - 1/z) * Z{X(s)/s}`
	**note:** no unstable poles and unstable zeros, no worries about constraints 2 and 3
2. [[Mapping between S-plane and Z-plane]]
	the relationship between Ts, order of system and zeta, omega
		1st order: G(s) = 1/(Ts+1)
		Ts = 4/T
		2nd order: G(s) = (w_n^2 / s^2 + 2zeta · w_n + w_n^2)
		Ts = 4/(zeta * w_n)
3. [[analog controller to digital]]
	pole-zeros matching
4. ![[Pasted image 20221103165930.png]]
# special cases
## finite setting time design
also a process of selecting G_cl
`G_cl(z) = z^-k`
k >= relative degree + intrinsic delay (exp(-s))

relative degree: num of poles - num of zeros
	if all poles and zeros of the discrete process are in the unit circle
#### dead beat control
![[Pasted image 20221104152703.png]]
may introduce oscillation

#### example
![[Pasted image 20221125183922.png]]
accquire G_zas:
![[Pasted image 20221125185916.png]]
- no intrinsic delay
- no unstable poles or zeros
accquire deadbeat controller:
	let`G_cl(z) = 1/z`
	**note: it is G_cl that has the z^-k form, not C(z)**
	and C(z)
	![[Pasted image 20221125190255.png]]

## ripple free controller
### design
maintain a control variable _U(z)_ after n samples, n == degree of the denominator
![[Pasted image 20221104225451.png]]
_U(z)_ is the ouput of C(z):
![[Pasted image 20221125190610.png]]
#6203_recite 
```
U(z) 
	= Y(z)/G_zas(z)
	= Y/R · R/G_zas
	= G_cl · R/G_zas
```
**U(z) consists of G_cl, R, G_zas**
G_cl is **unknown**, R, G_zas are known
we _design U(z)'s pattern according to n_
![[Pasted image 20221125190940.png]]
with _U(z)'s pattern_ (may have unknown coeff) and `U(z) = G_cl · R/G_zas`
we can determine `G_cl`

### example1
![[Pasted image 20221126174937.png]]
#### step1 derive G_zAS: _check_
#### step2 U(z) = G_cl(z) · R(z)/G_zAS(z) **forgot**
#### step3 Determine G_cl(z)'s pattern **dont know how**
#### step4 determine G_cl(z)'s coeff with G_cl(1) = 1 _check_
#### step5 calculate C(z) = 1/G_zAs · G_cl/(1-G_cl) **calculation error**

### example2 **no intgrator in G(s)**
![[Pasted image 20221126181612.png]]
#### step0  accquire g_zas(z) _provided if no (1/s) term_
#### step1 U(z) = G_cl · (R/G_zas)
#### step2 **E(z)=U(z)/C(z)=(1/C) · G_cl · (R/G_zAS)**
#6203_recite 
```
here, need to keep e(t) zero in n steps
E(z) = a0 + a1/z
```
C, G_cl needs designing
#### step3: design C **important trait of no integrator case**
#6203_recite 
```
C must contain an integrator, 1/(1-z^-1)
C contain another pole: 1/(1 - z1·z^-1)
a constant coeff: Kc
cancel out Denominator of G_zas: D_zas
```
**important:**
`C(z) = Kc · D_zas / ((1-z^-1)(1-z1 · z^-1))`
#### step4: design G_cl **depends on C's design**
now, E(z) is left with:
![[Pasted image 20221126221856.png]]
**important:**
G_cl should cancel out N_zAS
`G_cl = K·N_zAS`
determin K with G_cl(1) = 1