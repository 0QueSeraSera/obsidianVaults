In many cases, not all state variables can be accquired, need to estimate certain states with _limited_ observation `y = Cx`
where y's dimension is much smaller than x

**employ an _estimator_ to accquire full state x_hat
use the x_hat to feed the _controller_ **
![[Pasted image 20221205202204.png]]

# full state estimation
the full state estimator itself is a dynamical system
input: u, y
ouput: x_hatwww
```
x_hat_dot = A·x_hat + B·u + K_f · (y - y_hat)
y_hat = C · x_hat
```
`K_f · (y - y_hat)` is essentially an _update based on new data y_, this is going to correct x_hat
```
x_hat_dot = A·x_hat + B·u + K_f · (y - y_hat)
	= A·x_hat + B·u + K_f·y - K_f·C·x_hat
	 = (A - K_f·C)·x_hat + [B, K_f]·[u,y]T
```
with input being u and y, `[B, K_f]·[u,y]T` actually is like `B·u` term
dynamics of the esitmator is `(A - K_f·C)`

**when  `(A - K_f·C)` is stable, x_hat will stably converge to x**
## proof
define error: `epsilon = x - x_hat`, e for short
```
e_dot = x_dot - x_hat_dot
	= (A - K_f·C)e
```
![[Pasted image 20221205204905.png]]

**If obsv, we can place the eigs by choosing K_f**
# Kalman filter
with noise in system and measurement:
![[Pasted image 20221205205354.png]]
like lqr, the Kalman filter *balance* between measurement noise and system noise