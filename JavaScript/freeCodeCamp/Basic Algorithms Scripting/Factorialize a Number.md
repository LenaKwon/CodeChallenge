# Factorialize a Number
Return the factorial of the provided integer.

If the integer is represented with the letter `n`, a factorial is the product of all positive integers `less than` or `equal` to `n`.

Factorials are often represented with the shorthand notation `n!`
```javascript
For example: 5! = 1 * 2 * 3 * 4 * 5 = 120
```
Only integers greater than or equal to zero will be supplied to the function.

## Before
```javascript
function factorialize(num) {
  return num;
}

factorialize(5);
```
## Answers
```javascript
function factorialize(num) {
  let fact =1;
  for(let i = 2; i <= num; i++){
    fact *= i
  }
  return fact;
}

factorialize(5);
```
