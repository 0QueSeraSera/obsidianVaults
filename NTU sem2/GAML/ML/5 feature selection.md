![[Pasted image 20230409134314.png]]
# Individual Feature Evaluation
look at each feature's discriminatory capability.
## Fisher's Ratio
![[Pasted image 20230409134718.png]]
The numerator is _between-class_ difference. The denominator is _within-class scatter_.
The **larger** R the better: 
	larger between class difference
	smaller within-class scatter
## Mutual Information
![[Pasted image 20230409135057.png]]
`MI(x,y) = E(x) + E(y) - E(x,y)`
![[Pasted image 20230409135155.png]]

# Feature Subset Selection
Select a subset from a feature set to produce the best performance
![[Pasted image 20230409135505.png]]

## Search  methods
### Exhaustive Search
![[Pasted image 20230409135549.png]]

### Sequential Forward and Sequential Backward
![[Pasted image 20230409135844.png]]

## Evaluation Criterion
### Classification Results
![[Pasted image 20230409140143.png]]
Train classifiers on the subset
### Separability
![[Pasted image 20230409140257.png]]

#### Some separability measures
1. Distance calculation ![[Pasted image 20230409140417.png]]![[Pasted image 20230409140530.png]]
2. Scatter-based![[Pasted image 20230409140559.png]]
## Selection algorithms
consists of a _search method_ and an _eval criterion_
![[Pasted image 20230410150702.png]]
### Sequential Forward Feature Selection
Combining _Sequential forward Search_ and _evaluation criteria_
![[Pasted image 20230410152454.png]]
![[Pasted image 20230410152653.png]]
![[Pasted image 20230410152751.png]]
### Sequential Backward Feature Selection
![[Pasted image 20230410152821.png]]