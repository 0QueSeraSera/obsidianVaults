[[Chap5 Fitness, Selection, Population Management]]
****
# Survivor Selection
The [[Parent Selection]] decides who gets to mate
Survivor selection decides who gets to go to the next gen
Similar approaches
![[Pasted image 20230217121706.png]]
With generation change, 2 strategies:
- age based
- fitness based
## Fitness Based Replacement
A few strategies:
- Elitism: a few fittest get copied
- GENITOR: delete the worst, in contrast with Elitism
- Round-Robin![[Pasted image 20230220155529.png]]
- (lambda, mu) and (lambda + mu): the first selects _from children only_. The latter is from _both parents and children_
	- lambda,mu is better
![[Pasted image 20230217122121.png]]
![[Pasted image 20230217122248.png]]

