# Overview
Integral action is a control strategy used in Model Predictive Control (MPC) to _reduce steady-state errors_ and improve the _tracking performance of the system_. In MPC, the control actions are calculated by **solving an optimization problem based on a model of the system and a cost function**.

The integral action involves `adding an integral term to the cost function`, which is proportional to the accumulated error between the desired setpoint and the actual process variable. By doing so, the MPC controller can take into account the past error history and adjust the control actions to compensate for any steady-state error.

In other words, the integral action continuously _integrates the error signal over time_, which results in a larger control signal as the error persists. This way, the MPC controller can drive the process variable to the setpoint by gradually reducing the error to zero.

Overall, integral action is an important component of MPC that allows for better tracking and control of the system's behavior, especially when dealing with systems that have inherent steady-state errors.


# Requirements
1. in steady state, the _minimum_ of cost function must be consistent with zero tracking errors
2. predictions must be *unbiased*
![[Pasted image 20230403160027.png]]

## Cost Function Design
The incremental control form is valid.
judgement: whether `J = 0` is achieved when `y - w = 0` and `delta{u} = 0`
![[Pasted image 20230403160206.png]]
This does not meet the requirements. note the second term is `u` instead of `delta{u}`
![[Pasted image 20230403160235.png]]

Add the steady state into consideration. Now **when `J=0`, `y-w=0` and `u=u_ss`**, hence `delta{u} = 0`
![[Pasted image 20230403160545.png]]

## Unbiased
