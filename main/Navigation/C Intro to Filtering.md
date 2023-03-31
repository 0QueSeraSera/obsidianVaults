[[topic_LaserSLAM]]
****
# Bayes Filter
## Intro
Recall the motion scenario
![[Pasted image 20230309151916.png]]
In this scenario, the robot moves 100m, with 0.5 of chance to move exactly 100m, 0.25 to move 99m, 0.25 to move 101.
Here is the result of 2 moves
![[Pasted image 20230309152015.png]]
## Estimation and Measurement
![[Pasted image 20230309152134.png]]
motion model provides a distribution in position.
measurement of the distance to the landmarks can reflect on distance distribution as well.

Initially, we have a guess based on motion model `p(x)` (**Prior**)
given the real position, the measurement provides `p(z|x)`
what we want is the corrected estimation with measurement `p(x|z)` (**Posterier**)

![[Pasted image 20230309152431.png]]
## Bayes Filter
![[Pasted image 20230309152740.png]]
As shown in this diagram, define:
```
belief bel(x_t) = p(x_t)
bel__(x_t+1) = p(x_t+1)
```
![[Pasted image 20230309152844.png]]
The Bayes Filter repeats this updating process:
![[Pasted image 20230309153037.png]]
