# Overview
Cascade control can be applied when
- intermediate or secondary process is affected by disturbances
- or
- Secondary process's gain is non-linear
![[Pasted image 20230224104731.png]]
## Example
Here 1 primary **controlled var** (output)
2 possible secondary **manipulated var** (input)
![[Pasted image 20230224105015.png]]
This leads to the following arrangement:
![[Pasted image 20230224105354.png]]
primary output `y1` is on the outer loop
inner loop is the secondary var to _adjust setpoint_

# Cascade Structure and design
## Inner close loop TF
Given this block, derive the inner close loop TF
the output is y2, **input is u1 and d2**
Thus, the TF is:
`y2 = f(u1, d2)`
![[Pasted image 20230224105801.png]]

## Primary CL TF
## PID Cascade Control
![[Pasted image 20230224110920.png]]
### Example
![[Pasted image 20230224112240.png]]
The calculation is complex
![[Pasted image 20230224112533.png]]


### Summary
![[Pasted image 20230224112728.png]]


# Feedforward Control
## Overview
apply to measurable disturbances before affecting the output
Always used with feedback control
![[Pasted image 20230224124933.png]]
## Structure

# Other strategies
## Ratio control
![[Pasted image 20230224125307.png]]
## Split Range Control
![[Pasted image 20230224125427.png]]

