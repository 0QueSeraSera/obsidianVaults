[[control bootcamp]]
****
**What are the best eigenvalues?**
LQR
a cost function:
```
J = int{t,0,inf}([xT·Q·x + uT·R·u)dt]
```
`Q`: the penalty for not placing the poles at desired position
`R`: penalty for control effort

There is a **best** K with given Q and R, for controller `u = -Kx`
