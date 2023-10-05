# Sum All Odd Fibonacci Numbers
Given a positive integer `num`, return the sum of all odd Fibonacci numbers that are less than or equal to `num`.

The first two numbers in the Fibonacci sequence are `0` and `1`. Every additional number in the sequence is the `sum` of the two previous numbers. 
The first seven numbers of the Fibonacci sequence are `0, 1, 1, 2, 3, 5` and `8`.

For example, `sumFibs(10)` should return `10` because all odd Fibonacci numbers less than or equal to `10` are 1, 1, 3, and 5.

## Before
```javascript
function sumFibs(num) {
  return num;
}

sumFibs(4);
```
## Answers
```javascript
function sumFibs(num) {
  // Perform checks for the validity of the input
  if (num <= 0) return 0;

  // Create an array of fib numbers till num
  const arrFib = [1, 1];
  let nextFib = 0;

  // We put the new Fibonacci numbers to the front so we
  // don't need to calculate the length of the array on each
  // iteration
  while ((nextFib = arrFib[0] + arrFib[1]) <= num) {
    arrFib.unshift(nextFib);
  }

  // We filter the array to get the odd numbers and reduce them to get their sum.
  return arrFib.filter(x => x % 2 != 0).reduce((a, b) => a + b);
}

// test here
sumFibs(4);

sumFibs(4); //5
sumFibs(4000000) // 4613732
sumFibs(1000) //1785
```
