# Seek and Destroy
You will be provided with an `initial array` as the first argument to the destroyer function, followed by one or more arguments. 
Remove all elements from the initial array that are of the same value as these arguments.

The function must accept an *indeterminate* number of arguments, also known as a *variadic* function. 
You can access the additional arguments by adding a rest parameter to the function definition or using the arguments object.

## Before
```javascript
function destroyer(arr) {
  return arr;
}

destroyer([1, 2, 3, 1, 2, 3], 2, 3);
```
## Answers
```javascript
function destroyer(arr,...a) {
   return arr.filter(val=> ! a.includes(val))
}

destroyer([1, 2, 3, 1, 2, 3], 2, 3);
```
```javascript
function destroyer(arr) {
  const valsToRemove = Array.from(arguments).slice(1);
  return arr.filter(function(val) {
    return !valsToRemove.includes(val);
  });
}
 
```
### Code Explanation
1. Declare a variable named `valsToRemove` and set it equal to a *new Array object* `from()` the arguments passed into the function.
   Use the `slice()` method on the array of arguments, starting from the second index, 1.

2. Return the filtered array, using `includes()` in the callback function to check if `val` is not in `valsToRemove`;
   returning `true` to keep the value in the original array or `false` to remove it.


## Thinking
[arguments](https://forum.freecodecamp.org/t/how-arguments-work-in-javascript-javascript-arguments-guide/14283)</br>
[rest parameters](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/rest_parameters)</br>
[Array.prototype.includes()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/includes)</br>
