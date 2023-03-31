# Holdout method
Straightforward idea of taking a part as evaluation.
![[Pasted image 20230328102829.png]]
The division is _random_
## train-val-test split
validation set is used **during the training stage**.
test set is used **only once**.
![[Pasted image 20230328103044.png]]
## stratified random sampling
To deal with imbalanced data, take random samples *from each class*.
![[Pasted image 20230328111104.png]]

# Repeated Holdout method
To ensure _randomness_, employ multiple holdouts and take average
![[Pasted image 20230328111301.png]]

# K-Fold cross validation method
Divide the dataset into k portions. Each time _select one portion as test set_, **all of the rest are training set**.
In total, _k_ models are fit evaluated and take average.
![[Pasted image 20230328111527.png]]
The errors are taken average
![[Pasted image 20230328111925.png]]

# Leave-one-out cross validation (LOOCV)
k == total num of samples. Each fold only one sample is used as test set.
![[Pasted image 20230328112026.png]]
traits:
- maximizes the count of data used to train the model
- costly
- only fits cases when samples count is small

# Repeated k-fold-cross validation
