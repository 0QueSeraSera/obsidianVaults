a pair of graph
one for frequency-phase, another for frequency-gain (in dB)

**note: in steady state response, s = jw, sigma is set to be 0. sigma is corresponds to exponential term and dies out**

![[Pasted image 20221029121322.png]]
set s = jw, gain is the length of the vector and phase is the angle
rotating the vector, actually simulates the bode plot
****
## sketching Bode plot by hand
**important: know how a pole or a zero affects the system behaviour**
### real constants
	transfer function: H(s) = K
	gain = |H(jw)| = abs(K)
	phase = arg(H(jw)) = atan2(0,K)
![[Pasted image 20221029122036.png]]
### poles and zeros at origin
	pole at origin
		H(jw) = 1/(jw) = -j(1/w)
		real part: 0, imag part: -1/w
		**refers to real and imag part** 
		gain = 1/w, phase = arg(-1/w, 0) = -90deg
		
	zero at origin
	H(jw) = jw = 1/(1/jw)	==> 1 - pole at origin
![[Pasted image 20221029122720.png]

### real poles and zeros
![[Pasted image 20221029154918.png]]
after setting s = jw, we have:
- gain = -20log(sqrt(1+w^2/w_0^2))
- phase = atan(-w/w_0)
we have 3 sections of drawing:
![[Pasted image 20221029155359.png]]

simplification (pink lines):
![[Pasted image 20221029155504.png]]

**summary:**
1. find w_0, in form of 1 / (1 + s / w_0)
2. in gain plot, only one key point: w_0. in phase plot, spot 0.1 w_0 and 10w_0
3. gain plot has 2 line segmentations, phase plot has 3.
### complex poles and zeros
#### intro: why a pare of complex poles and zeros and what this means for a physical system?
![[Pasted image 20221029160407.png]]
*damping ratio zeta:* 
	if <1, system oscillates, has complex roots
	if >1, system behaves in a exponential way
#### bode plot drawing
*note: there are trivial errors*
![[Pasted image 20221029160734.png]]
like dealing with real poles and zeros, break this into 3 sections
![[Pasted image 20221029161032.png]]
![[Pasted image 20221029161201.png]]


****

