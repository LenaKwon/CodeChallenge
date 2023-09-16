# Finders Keepers
Create a function that looks through an array `arr` and returns the first element in it that passes a `'truth test'`. 
This means that given an element `x`, the `'truth test'` is passed if `func(x)` is `true`. If no element passes the test, return undefined.

## Before
```javascript
function findElement(arr, func) {
  let num = 0;
  return num;
}

findElement([1, 2, 3, 4], num => num % 2 === 0);
```
## Answers
```javascript
function findElement(arr, func) {
  for(let i = 0; i < arr.length; i++){
  let num = arr[i];
  if(func(num)) retrun num;
  }
  return undefined;
}

findElement([1, 2, 3, 4], num => num % 2 === 0);
```
## Note
Study features for `return`
1. Value can be returned at the point you call the function.
2. When the function meets the return value, execution of function is stopped immediately and return the value.
3. Can clarify `return` itself without value and execution of function is stopped immediately.'
4. If the function does not have return or return itself, it will return undefined.
5. Cannot add any code after return.
