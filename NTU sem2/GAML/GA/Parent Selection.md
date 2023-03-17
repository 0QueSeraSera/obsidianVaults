[[Selection]]
****
# Parent Selection
## Fitness Proportional Selection (FPS)
Probability of a individual selected for **MATING** is _proportional_ to its fitness
![[Pasted image 20230217120617.png]]
problems:
- one high fit member take over rapidly (like environment with small diversity)
- loss of [[Selection Pressure]], convergence rate becomes much slower
![[Pasted image 20230220153417.png]]
- ineffective when changing the fitness function (due to its _linearity_)
![[Pasted image 20230220153735.png]]


## Rank-based Selection
Use **relative** fitness
![[Pasted image 20230217120934.png]]
This thinking yields different methods of measuring ranking:
linear, exponential
### Linear Ranking
![[Pasted image 20230217120958.png]]
### Exponential Ranking
![[Pasted image 20230217121025.png]]

## Tournament Selection
Trait: Only Use **Local** Fitness Information, not relying on **global statistics**
![[Pasted image 20230217121322.png]]
Factors:
The larger k means a wider range of competing. The better candidates will have better chance of winning out [[Selection Pressure]]

	![[Pasted image 20230217121442.png]]
	

## Uniform
![[Pasted image 20230217121533.png]]
