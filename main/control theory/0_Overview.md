[[control bootcamp]]
****
control category:
passive -- active
active (with energy input):
	closed loop -- open loop

why feedback?
1. uncertainty
2. instability
	- open loop cannot change the dynamic of the system
3. disturbances
4. efficiency

feedback control's capability of changing the system
state_space model:
use a _linear differential equation_ to discribe the system:
`x_dot = Ax`
**solution** to this is `x(t) = exp(At)·x(0)`
A with positive **eigen values** will lead to **unstable** system (t->inf)

Then, add an _input_ `Bu`
`x_dot = Ax + Bu`

Then, _measure_ some _state_ `y = Cx`

suppose u = -Kx,
`x_dot = (A - BK)x` with **changes** system dynamics
from A to A - BK
