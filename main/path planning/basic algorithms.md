[[Sampling based path searching]]
****
Base method:
[[RRT]]
- **uniformly, randomly** generate new sampling points *(sp for short)*
- connect with the nearest existing points

A Bi-directional search: [[RRT-Connect]]

Base method for path optimization: [[RRT-star]]

Possible improvement:
- sampling stretagies
- reducing tree nodes
- optimizing paths
**Note: These methods optimizes paths gradually, depending on iteration times**
RRT* recent variants：
[[RRT-star-Smart]]
	reduces node with #triangle_inequality 
	generate nodes **close to obstacle vertices** #visibility_graph
both [[RRT-star-Smart]] and [[RRT-star]] has O(n), O(nlogn) complexity in space and time, but [[RRT-star-Smart]] has smaller n
[[Q-RRT-star]]	
	optimize path with #triangle_inequality 
	increased the number of potential parents compared with [[RRT-star-Smart]]

Applying Heuristics:
[[Informed-RRT-star]] 
	form an elliptical sampling region
[[Batch Informed Trees]]
	
[[Adaptively Informed Trees (AIT-star)]]