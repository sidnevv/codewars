Task:  

Create an endless stream of prime numbers - a bit like ```IntStream.of(2, 3, 5, 7, 11, 13, 17)```, but infinite. The stream must be able to produce a million primes in a few seconds.  

Solution:

```js
class Primes {
    static * stream() {
        let n = 1;
        yield 2;
        while(true) {
            n = n + 2;
            if (checkNumbers(n)) {
                yield n;
            }  
        }
    }
}

let checkNumbers = (n) => {
    for (let i = 3; i <= Math.sqrt(n); i = i + 2) {
        if (n % i === 0) {
            return false;
        }
    }
    return true;
}
```

