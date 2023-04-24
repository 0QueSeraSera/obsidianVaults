[[Chap5 Fitness, Selection, Population Management]]
****
2 types:
Generational model, Steady-state model
In the first model, all individual survives only one gen
In the second, **one** new offspring generated and **one** individual gets replaced
#concept **Generation Gap**: the proportion of replaced indi.
1.0 for GGA, 1/popu_size for SSGA
# Generational Model
![[Pasted image 20230217115831.png]]
![[Pasted image 20230218180114.png]]
- Complete replacement
- each individual survives for 1 gen
- 

# Steady-State model:
	![[Pasted image 20230217115907.png]]
![[Pasted image 20230218180249.png]]
Changed gradually.
**Generational gap** = `lambda / mu`
*lambda* parents are replaced with *lambda* offsprings
Often, `lambda == 1`
Meaning:
![[Pasted image 20230217115955.png]]
