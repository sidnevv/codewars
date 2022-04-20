Task:  

Given two congruent circles a and b of radius r, return the area of their intersection rounded down to the nearest integer.  

Code Limit: Less than 94 characters.

Example:  

For ```c1 = [0, 0], c2 = [7, 0] and r = 5```, the output should be ```14```.  

Solution:

```js
with(Math)circleIntersection=([a,b],[c,d],r)=>(-sin(f=2*acos(hypot(a-c,b-d)/(2*r)))+f)*r*r|0
```
