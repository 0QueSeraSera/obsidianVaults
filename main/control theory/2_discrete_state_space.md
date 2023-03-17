[[modern control basics]]
****
# Discrete-time SS model with sample and hold

![[Pasted image 20221123155537.png]]
#6203_recite 
1. calculate `Phi(t) = invL{inv([sI-A])}`
2. Ad = Phi(T)
3. Bd = `int(0,T){phi(t)}B`
4. Cd = C, Dd = D
# discrete transfer functions
![[Pasted image 20221123155932.png]]
## poles and zeros
### poles
like continuous case:
![[Pasted image 20221123160015.png]]
### zeros: 
==system output is 0== when input and state are not 0
<==>
find X(z0), U(z0) that are 0, and Y(z0) is 0. z0 is ==a zero of the system==
Given:
![[Pasted image 20221123160829.png]]
we have ![[Pasted image 20221123160841.png]]
![[Pasted image 20221123160853.png]]

# state transition equation
a recursion method of solving the state equation
to obtain the ss model from differential equation:
==find relations between x(k) and x(k+1)==
![[Pasted image 20221123161723.png]]

# similarity transfrom
apply the linear transformation:
`x(k) = Pw(k)`
then
`w(k) = inv(P).x(k)`
![[Pasted image 20221123162255.png]]
becomes:
![[Pasted image 20221123162317.png]]
property:
	transfer function is invariant





