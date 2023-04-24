specially written for EE6221, not systematical
****
# Modelling
![[Pasted image 20230423225722.png]]
![[Pasted image 20230423224713.png]]
`w` and `v` are _uncorrelated_, _zero-mean_, _Gaussian noise_
![[Pasted image 20230423224849.png]]

# KF Formula
![[Pasted image 20230423225539.png]]
![[Pasted image 20230423225619.png]]

## Derivation
![[Pasted image 20230424105443.png]]
![[Pasted image 20230424105602.png]]
![[Pasted image 20230424105729.png]]
# Example
![[Pasted image 20230423232207.png]]
![[Pasted image 20230423232214.png]]
## Batch Processing
![[Pasted image 20230423232323.png]]
Form the KF expression for estimate `x_k+1`
`hat{x_k+1} = hat{x_k} + Kk * (z_k - H*hat{x_k})`
**Minimize the variance of estimate error**
**`~x_k+1 = x_k+1 - ^x_k+1`**
![[Pasted image 20230423232405.png]]
Note the variance calculation here. **Assume `E{~x_k+1} = 0`**
thus `P_k+1 = E{(~x_k+1)^2}`
![[Pasted image 20230423232751.png]]

Expand the formula and all cross-correlation terms are 0
![[Pasted image 20230423232934.png]]

Minimize `P_k+1` wrt `K1`, `K2`
![[Pasted image 20230423233106.png]]
The solution is acquired
![[Pasted image 20230423233155.png]]

## Sequential Processing
![[Pasted image 20230423234104.png]]