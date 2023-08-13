[[Bode plot]]
[[frequency response design]]
****
# criteria
1. phase margin
3. gain margin
4. gain crossover
5. bandwidth
6. steady state error
![[Pasted image 20221029163056.png]]

# Types and Design
## types
![[Pasted image 20221101104205.png]]
## Lead compensator design
- to improve transient performance
`C(s) = KC_0(s) = S(Ts+1)/(aTs+1)`
![[Pasted image 20221101104525.png]]
### procedure
1. compensator gain K meets steady-state error:`K_p = lim(s->0){KG(s)}`
2. draw [[Bode plot]] of KG(s)
3. determine phase lead Phi:![[Pasted image 20221101104922.png]]![[Pasted image 20221101110504.png]]
4. from Phi, get a
		`a = (1-sin(Phi))/(1+sin(Phi))`
5. get omega_g':![[Pasted image 20221101110814.png]]
6. C(s) = K(Ts+1)/(aTs+1). verify the [[Bode plot]] of C(s)G(s)
#### summary: 
	![[Pasted image 20221101110939.png]]

