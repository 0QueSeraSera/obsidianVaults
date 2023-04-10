# Evaluation methods
## Holdout method
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

## Repeated Holdout method
To ensure _randomness_, employ multiple holdouts and take average
![[Pasted image 20230328111301.png]]

## K-Fold cross validation method
Divide the dataset into k portions. Each time _select one portion as test set_, **all of the rest are training set**.
In total, _k_ models are fit evaluated and **take average**.
![[Pasted image 20230328111527.png]]
The errors are taken average
![[Pasted image 20230328111925.png]]

## Leave-one-out cross validation (LOOCV)
k == total num of samples. Each fold only one sample is used as test set.
![[Pasted image 20230328112026.png]]
traits:
- maximizes the count of data used to train the model
- costly
- only fits cases when samples count is small

## Repeated k-fold-cross validation
normal K-fold method will get different mean with different selected groups
![[Pasted image 20230410124023.png]]
One solution is to repeat k-fold. Evaluate performances on all folds and all repeats
![[Pasted image 20230410124148.png]]

Its procedure goes like this.
After each iteration, the data is reshuffled.
![[Pasted image 20230410124317.png]]


# Evaluation Metrics
for a binary classification, 4 results are possible
True results (**TP, TN**) are _correctly_ classified
False results (**FP, FN**) are **wrongly** classified, the real class is the opposite of the named value. Like _FP_ is actually a **negative** sample
![[Pasted image 20230410124549.png]]
A 2X2 matrix based on 4 possible outcome
![[Pasted image 20230410124720.png]]
## A few metrics
![[Pasted image 20230410124836.png]]
### Accuracy and Error Rate
`Acc = (TP + TN) / (TP + FP + TN + FN)`
`Err = (FP + FN) / (TP + FP + TN + FN)`
These 2 directly shows the portion of *correct* classification and *wrong* classification

### Sensitivity and Specificity
Sensitivity focuses on positive _samples_
Specificity focuses on **negative** _samples_
In contrast with the **Precision** and **Recall**
![[Pasted image 20230410125525.png]]
![[Pasted image 20230410125611.png]]

### Precision and Recall
Precision calculates the **correct rate** of all positive **predictions**
Recall calculates the proportion of correctly predicted samples among all positive samples
Their _numerators_ are both **TP**
	Precision measures against all positive **predictions**
	Recall measures against all positive **samples**
![[Pasted image 20230410130254.png]]

### F-Score
![[Pasted image 20230410130601.png]]
```
F = (2 x Precision x Recall) / (Precision + Recall)
```


## ROC Curve
![[Pasted image 20230410131249.png]]
![[Pasted image 20230410145622.png]]
