# Sum All Primes
A prime number is a whole number greater than 1 with exactly two divisors: 1 and itself. For example, 2 is a prime number because it is only divisible by 1 and 2. 
In contrast, 4 is not prime since it is divisible by 1, 2 and 4.

Rewrite `sumPrimes` so it returns the sum of all prime numbers that are less than or equal to `num`.

## Before
```javascript
function sumPrimes(num) {
  return num;
}

sumPrimes(10);
```
## Answers
```javascript
function sumPrimes(num) {
    let sum = 0;

    function isPrime(i){
        for(let k = 2; k < i; k++){
            if(i%k ==0){
                return false;
            }
        }
        return true;
    }

   for(let i=2; i<=num; i++){
        if(isPrime(i)){
           sum += i;
        }
    }return sum;
}
sumPrimes(10);
```

## Note 
Nomally the number that can be divided by `2` is Not the prime number.
`2` is only even number in prime numbers.

In this case using `order of execution` of `for` loop to add `2` to the prime number group which is mostly not divided by `2`.
For loop in the `isPrime` function above , firstly initialisation `k = 2` executed, then condition expression `k < i` is evaluated next. 
At first iteration, the condition expression is like `2 < 2` it is false, so execution is terminated even before reaching statement. 
(if it reachs the statement it will return `false`)
As a result, it will return value of `true` which is set out of `for` loop as a return value.
Therefore the second for loop can add the first value of `i = 2` to the sum as isPrime() function is `true`. 

## Other solution
```javascript
function sumPrimes(num) {
  // Helper function to check primality
  function isPrime(num) {
    const sqrt = Math.sqrt(num);
    for (let i = 2; i <= sqrt; i++) {
      if (num % i === 0)
        return false;
    }
    return true;
  }

  // Check all numbers for primality
  let sum = 0;
  for (let i = 2; i <= num; i++) {
    if (isPrime(i))
      sum += i;
  }
  return sum;
}
```
```javascript
function sumPrimes(num) {
  // Check all numbers for primality
  let primes = [];
  for (let i = 2; i <= num; i++) {
    if (primes.every((prime) => i % prime !== 0))
      primes.push(i);
  }
  return primes.reduce((sum, prime) => sum + prime, 0);
}
```
```javascript
function sumPrimes(num) {
  // Prime number sieve
  let isPrime = Array(num + 1).fill(true);
  // 0 and 1 are not prime
  isPrime[0] = false;
  isPrime[1] = false;
  for (let i = 2; i <= Math.sqrt(num); i++) {
    if (isPrime[i]) {
      // i has not been marked false -- it is prime
      for (let j = i * i; j <= num; j += i)
        isPrime[j] = false;
    }
  }

  // Sum all values still marked prime
  return isPrime.reduce(
    (sum, prime, index) => prime ? sum + index : sum, 0
  );
}
```
