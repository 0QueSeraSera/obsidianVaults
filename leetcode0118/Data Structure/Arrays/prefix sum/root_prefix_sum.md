[[root_Arrays]]
****
#prefix-sum 
prefix-sum is essentially the accumulated sum
```
psum[i] = psum[i-1] + n[i-1]
psum[0] = null
psum[1] = n[0]
psum[2] = n[0] + n[1]
...
```
This can easily calculate the sum of a segment of array
features:
- the original array is constant
- frequently enquiry