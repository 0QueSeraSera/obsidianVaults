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
To ensure _randomness_, employ multiple holdouts and **take average**
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
**After each iteration, the data is reshuffled**. In each epoch, the data combination is different
![[Pasted image 20230410124317.png]]


# Evaluation Metrics
for a binary classification, 4 results are possible
True results (**TP, TN**) are _correctly_ classified (starts with `T`)
False results (**FP, FN**) are **wrongly** classified, the real class is the opposite (starts with `F`) of the named value. Like _FP_ is actually a **negative** sample
![[Pasted image 20230410124549.png]]
A 2X2 matrix based on 4 possible outcome
![[Pasted image 20230410124720.png]]
## A few metrics
![[Pasted image 20230410124836.png]]
### Accuracy and Error Rate
- The only two that focus on **global** rate
- The denominator is the whole scenario
`Acc = (TP + TN) / (TP + FP + TN + FN)`
`Err = (FP + FN) / (TP + FP + TN + FN)`
These 2 directly shows the portion of *correct* classification and *wrong* classification

### Sensitivity and Specificity
- D is based on _sample_ classes, instead of _predictions_
- In contrast with the **Recall**
Sensitivity focuses on positive _samples_
Specificity focuses on **negative** _samples_
![[Pasted image 20230410125525.png]]
![[Pasted image 20230410125611.png]]

### Precision and Recall
Precision calculates the **correct rate** of all positive **predictions**
Recall calculates the proportion of correctly predicted samples among all positive samples

Both N is `TP`, D is different
Their _numerators_ are both **TP**
	Precision measures against all positive **predictions**
	Recall measures against all positive **samples**
![[Pasted image 20230410130254.png]]
![[Pasted image 20230410170848.png]]
![[Pasted image 20230410171106.png]]
### F-Score
![[Pasted image 20230410130601.png]]
```
F = (2 x Precision x Recall) / (Precision + Recall)
```


## ROC Curve
A evaluation method about the **threshold** _for a sample to be positive_
![[Pasted image 20230425112017.png]]

![[Pasted image 20230426111250.png]]
The TPR and FPR consist of the Y and X axis respectively.
different threshold will give different ratio
A: TPR == FPR == 1 ==> FN == 0, TN == 0 ==>
![[Pasted image 20230425111529.png]]

![[Pasted image 20230410145622.png]]

### Illustration
https://www.youtube.com/watch?v=4jRBRDbJemM
To classify as obese or not obese. First look at 0.5 threshold.
![[Pasted image 20230425114147.png]]
Acquire the confusion matrix. 
from the 8 samples on horizontal axis, 
- 4 is classified as false, 3 out of 4 is correctly classified (_TN_), 1 is wrong (*FN*)
- 4 is classified as true, 3 is correct (*TP*), 1 is wrong (_FP_)
`TPR = TP / (TP + FN) = 3/4`
`FPR = FP / (TN + FP) = 1/4`
**The larger Y while smaller X is preffered. This can help with determining the formula**
![[Pasted image 20230425114325.png]]
