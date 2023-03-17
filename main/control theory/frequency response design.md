[[design of the discrete control system]]
****
# overview
- trial-and-error
- based on Bode plots [[Bode plot]]
- to get the frequency response of G(z),==substitute z = exp(j omega T)==
- use bilinear transformation [[analog controller to digital]]
## Bilinear Transformation and w-plane
w <--> z:
	z = (1 + wT/w) / (1 - wT/2)
	w = (2z - 1) / (Tz + 1)
let `v = Im[w]`

# design procedure
given G(s)
1. G(s) --> G_zAS(z)
2. G_zAS --> G(w)
3. draw [[Bode plot]] of G(jv), use analog methods to design a controller C(w) or G_D(w)
4. C(w) --> C(z)
5. varify the performance
# [[compensator design]]

# An example
...