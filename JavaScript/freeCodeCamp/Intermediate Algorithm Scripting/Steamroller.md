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
