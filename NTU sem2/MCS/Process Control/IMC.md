[[Chap2]]
****

# Overview
DSM has problems:
- Unkownm plant 
- not realizable
![[Pasted image 20230219212731.png]]

**Internal model control** is also based on **_assumed plant model_**
## Diagram
![[Pasted image 20230219212943.png]]
IMC added a `G~` as the internal model. It leads to errors `E` being different
notes:
	`G~` and `G` are usually not identical
	![[Pasted image 20230219213139.png]]
Derivation of the TF, `Y = f(R, L)`
![[Pasted image 20230224155413.png]]

# IMC design Synthesis
Study the case when G~ = G
```
Y = G_c* · G · R + (1 - G_c*·G)L
```
`G_c*` is the controller
### step1 -- refactor
Essentially about seperating **time delay** and **rhp zeros**
`G~+` also satisfies: `G~+(s=0) = 1`
![[Pasted image 20230224155801.png]]
### step2 Derive Controller G_c*
The controller is equal to LPF filtered inverse of `G~_`
#recite 
![[Pasted image 20230224155930.png]]
### step3 derive the closed loop TF
![[Pasted image 20230224160105.png]]
### example
1. refactor the G~, **seperate _time delay_ and _rhp zeros_**
2. derive the controller
3. derive the conventional controller #recite 
```
G~ --> G~ = G-~·G+~ --> G_c* = f/G_~ --> G_c = G_c* / (1-G_c*G~)
```
![[Pasted image 20230224160649.png]]


## IMC Tuning
### Lag Dominant model
Traits:
- relative small time delay
- satisfactory set point response, bad disturbances response
### Several solutions:
1. ![[Pasted image 20230224161858.png]]
2. ![[Pasted image 20230224161915.png]]
3. ![[Pasted image 20230224161932.png]]
4. 


