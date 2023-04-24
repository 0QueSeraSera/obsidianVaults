# Clustering
![[Pasted image 20230403231126.png]]
## Centroid-Based Methods
### Concepts
Hierarchical clustering
![[Pasted image 20230403231310.png]]
Density based clustering
![[Pasted image 20230403231441.png]]

Distribution based clustering
![[Pasted image 20230403231754.png]]



### K-means
![[Pasted image 20230403231924.png]]
#### Criterion
WCSS
k clusters with k different `mean`
all samples
**Sum** over all samples' differences with all `mean` values
![[Pasted image 20230403232148.png]]
WCSS measures the **total squared error**
the mean vector is the _best representative_ of each clusters
![[Pasted image 20230403232409.png]]

#### Procedure
2 main operations:
- Init k clusters with *randomly* selected k samples
- Assign Samples to the nearest cluster
- Compute new cluster centroids
procedure:
1. ![[Pasted image 20230405180710.png]]
2. ![[Pasted image 20230405180732.png]]
3. ![[Pasted image 20230405180739.png]]
4. ![[Pasted image 20230405180814.png]]It will **reach a steady state** at last
#### Elbow Methods
![[Pasted image 20230405181323.png]]

## Hierarchical Clustering
2 approaches for hierarchical clustering
![[Pasted image 20230405182523.png]]
Note that the bottom layer **contains only one sample exactly**.

### Agglomeration
in summary, it follows:
1. consider each sample as a cluster
2. take 2 closest samples and merge them into 1 cluster
3. repeat until there is only 1 cluster
![[Pasted image 20230405222103.png]]

#### Detailed Procedure:
![[Pasted image 20230405182858.png]]
![[Pasted image 20230405183007.png]]
After a _new_ cluster is formed, there are a few ways to measure its similarity (the original features are not directly available)
1. Single linkage![[Pasted image 20230405183639.png]]
2. complete linkage (still *pairwise sample* distance)![[Pasted image 20230405183722.png]]
3. Centroid linkage![[Pasted image 20230405183852.png]]
4. ![[Pasted image 20230405183959.png]]
### An  example:
#### 1. Merge the closet to form a new cluster
![[Pasted image 20230405182912.png]]
![[Pasted image 20230405182925.png]]
![[Pasted image 20230405183142.png]]
#### 2. Determine the distance from the new cluster to other clusters
After a new cluster is merged, the new cluster's property can be determined with.
In summary
- Single linkage and complete linkage **use single sample** from each cluster and take the _minimum/maximum_
- Average linkage take _average_ of **single sample**'s distance
- Centroid linkage calculate each cluster's **center** then calculate the centroids distance.

1. **Single linkage** (Nearest Neighbour). This needs to be _repeated_ _over all other clusters_. Each time, every samples in the newly merged cluster needs to be checked.
![[Pasted image 20230410162333.png]] 
![[Pasted image 20230410163211.png]]
2. **Complete Linkage (farthest neighbour)** ![[Pasted image 20230410162536.png]]
3. **Centroid linkage**![[Pasted image 20230410162639.png]]
![[Pasted image 20230410162907.png]]
4. **Average Linkage**![[Pasted image 20230410163620.png]]


## Density-based clustering
https://www.youtube.com/watch?v=RDZUdRSDOok
a cluster is build with a core point. Among its neighbours, if a sample is a core point (_core_), it is added to the cluster and repeat the same adding process. If a neighbour sample is not a core point (_border_), it is only added to the cluster **but not being expanded around it**.
### Overview 
DBSCAN is based on _density_, unlike K-means, it divides samples into **noise and clusters**
![[Pasted image 20230405222413.png]]
### Features
It has 2 important params: 
![[Pasted image 20230405222826.png]]
and 3 types of data points:
![[Pasted image 20230405222944.png]]

3 types of relationship:
directly density reachable,  density-reachable, 
1. ![[Pasted image 20230405223243.png]]
2. ![[Pasted image 20230405223308.png]]
3. ![[Pasted image 20230405223350.png]]

### Param selection and procedure
`MinPt` 
- larger value for noisy data
- `MinPt >= D + 1, MinPt >= 2 * D`
`sigma`
- general small values are preferred
Procedure:
![[Pasted image 20230405224012.png]]
In contrast with k-means, DBSCAN starts with only *1* sample