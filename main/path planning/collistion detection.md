http://lavalle.pl/planning/node211.html
# Two-phase collision detection
## 1. broad phase
In the _broad phase_, the task is to avoid performing expensive computations for bodies that are far away from each other. Simple bounding boxes can be placed around each of the bodies, and simple tests can be performed to avoid costly collision checking unless the boxes overlap. Hashing schemes can be employed in some cases to greatly reduce the number of pairs of boxes that have to be tested for overlap [[703](http://lavalle.pl/planning/node858.html#Mir98)]. For a robot that consists of multiple bodies, the pairs of bodies that should be considered for collision must be specified in advance, as described in Section [4.3.1](http://lavalle.pl/planning/node157.html#sec:defbmp).

## 2. narrow phase
### 2.1 Hierarchical Methods
_Hierarchical methods_ generally decompose each body into a tree. Each vertex in the tree represents a ==_bounding region_== that contains some subset of the body. The bounding region of the root vertex contains the whole body.
![[Pasted image 20221113173800.png]]
