# Overview
Integral action is a control strategy used in Model Predictive Control (MPC) to _reduce steady-state errors_ and improve the _tracking performance of the system_. In MPC, the control actions are calculated by **solving an optimization problem based on a model of the system and a cost function**.

The integral action involves `adding an integral term to the cost function`, which is proportional to the accumulated error between the desired setpoint and the actual process variable. By doing so, the MPC controller can take into account the past error history and adjust the control actions to compensate for any steady-state error.

In other words, the integral action continuously _integrates the error signal over time_, which results in a larger control signal as the error persists. This way, the MPC controller can drive the process variable to the setpoint by gradually reducing the error to zero.

Overall, integral action is an important component of MPC that allows for better tracking and control of the system's behavior, especially when dealing with systems that have inherent steady-state errors.

# Review on Cost Functions
## Requirement for the Cost Functions
![[Pasted image 20230403160027.png]]
## Cost Function Design
The incremental control form is valid.
![[Pasted image 20230403160206.png]]
This does not meet the requirements
![[Pasted image 20230403160235.png]]

Add the steady state into consideration:
![[Pasted image 20230403160545.png]]
