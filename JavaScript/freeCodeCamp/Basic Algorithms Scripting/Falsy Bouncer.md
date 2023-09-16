# Falsy Bouncer
Remove all falsy values from an array. Return a new array; do not mutate the original array.

Falsy values in JavaScript are false, null, 0, "", undefined, and NaN.

Hint: Try converting each value to a Boolean.

## Before
```javascript
function bouncer(arr) {
  return arr;
}

bouncer([7, "ate", "", false, 9]);
```
## Answers
```javascript
function bouncer(arr) {
  const filteredArr = [];
  for (let i = 0; i < arr.length; i++) {
    if (arr[i]) filteredArr.push(arr[i]);
  }
  return filteredArr;
}
bouncer([7, "ate", "", false, 9]);
```

## Note
We use the if statement to check if the current element is truthy or falsy. </br>
(Don't need to right down all the falsy condition in the if statement...)


## Other Solution
```javascript
function bouncer(arr) {
  return arr.filter(Boolean);
}
```
### Code Explanation
The `Array.prototype.filter` method expects a function that returns a `Boolean` value which takes a single argument 
and returns `true` for truthy value or `false` for falsy value. Hence we pass the `built-in Boolean function`.
