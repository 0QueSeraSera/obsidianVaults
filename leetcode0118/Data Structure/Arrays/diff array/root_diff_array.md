[[root_Arrays]]
****
# Basic
![[Pasted image 20230323115245.png]]
Application: frequently add/substract **a segment of array**

![[Pasted image 20230323115343.png]]
Similar to prefix sum, the diff stores info about adjacent elements.
here, it stores the _difference_
while prefix sum stores the _accumulated sum_
and diff array has the **same size** with the original array
The _first element is the same_, the rest are the differences

# How to Use
original:
![[Pasted image 20230323120411.png]]

apply modification to a segment `[i~j]`:
![[Pasted image 20230323120419.png]]

Modify the diff array multiple times, with each time's cost of O(1), then reconstruct the original array.
![[Pasted image 20230323120640.png]]

