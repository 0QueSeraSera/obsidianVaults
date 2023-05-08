[[Chap5 Fitness, Selection, Population Management]]
****
Selection happens in both parent mating and (parent + offspring) survivor
![[Pasted image 20230217120402.png]]
# Parent Selection
## Fitness Proportional Selection (FPS)
_Probability_ of a individual selected for mating is _proportional_ to its fitness
![[Pasted image 20230217120617.png]]
problems:
- one high fit member take over rapidly (like environment with small diversity)
- loss of [[Selection Pressure]], convergence rate becomes much slower
#concept Selection Pressure: 
```
Selection pressure refers to the degree to which "fit" individuals are favored over "less fit" individuals.
```
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
![[Pasted image 20230217121442.png]]

## Uniform
![[Pasted image 20230217121533.png]]

# Survivor Selction
The Parent Selection decides who gets to mate
Survivor selection decides who gets to go to the next gen
Similar approaches
![[Pasted image 20230217121706.png]]
With generation change, 2 strategies:
- age based: not considering fitness, one way: delete the oldest
- fitness based: 
## Fitness Based Replacement
![[Pasted image 20230217122121.png]]
A few strategies:
- **Elitism**: a few fittest get copied
- **GENITOR**: delete the worst, in contrast with Elitism
- **Round-Robin**: every individuals are competed against `q` other individuals, regardless of parents or offsprings. Select top `mu` ones with most winning

Some more strategies:
_straightforward ranking based on fitness_
(lambda, mu) and (lambda + mu): the first selects _from children only_. The latter is from _both parents and children_
	- lambda,mu is better

![[Pasted image 20230217122248.png]]




