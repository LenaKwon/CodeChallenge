# Steamroller
Flatten a nested array. You must account for varying levels of nesting.

## Before
```javascript
function steamrollArray(arr) {
  return arr;
}

steamrollArray([1, [2], [3, [[4]]]]);
```
## Answers
```javascript
function steamrollArray(arr) {
    return arr
    .toString()
    .replace(",,",",")
    .split(",")
    .map (function(v){
        if(v=='[object Object]'){
            return {};
        }else if(isNaN(v)){
            return v;
        }else {
            return parseInt(v)
        }
    }); 
} 
steamrollArray([1, [2], [3, [[4]]]]);
```
## Other solutions
```javascript
function steamrollArray(arr) {
  const flat = [].concat(...arr);
  return flat.some(Array.isArray) ? steamrollArray(flat) : flat;
}

steamrollArray([1, [2], [3, [[4]]]]);
```
## Code Explanation
Use spread operator to concatenate each element of `arr` with an empty array </br>
Use Array.some() method to find out if the new array contains an array still</br>
If it does, use recursion to call steamrollArray again, passing in the new array to repeat the process on the arrays that were deeply nested</br>
If it does not, return the flattened array</br>

