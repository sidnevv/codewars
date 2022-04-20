Task:

Given the string representations of two integers, return the string representation of the sum of those integers.

Example:

```sumStrings('1','2') // => '3' ``` 

A string representation of an integer will contain no characters besides the ten numerals "0" to "9".

Solution:  

```js
function sumStrings(a,b) {
    const arr1 = a.split('');
    const arr2 = b.split('');
    let result = [];
    let t = 0;
    arr1.reverse();
    arr2.reverse();
    for(let i = 0 ; i <= Math.max(arr1.length, arr2.length)-1; i++) {
        let sum = (+arr1[i] || 0) + (+arr2[i] || 0) + t;
        if (sum >= 10) {
            let d = sum - 10;
            t = 1;
            result.push(d);
        } else {
            t = 0;
            result.push(sum);
        }
    };
    t === 1 ? result.push(t) : '';
    return result.reverse().join('').replace(/^0+/, '');
}
```
