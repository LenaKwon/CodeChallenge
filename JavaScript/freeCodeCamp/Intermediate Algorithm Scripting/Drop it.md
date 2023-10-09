# Drop it
Given the array `arr`, iterate through and remove each element starting from the first element (the 0 index) until the function `func` returns `true` when the iterated element is passed through it.

Then return the rest of the array once the condition is satisfied, otherwise,  `arr` should be returned as an empty array.

## Before
```javascript
function dropElements(arr, func) {
  return arr;
}

dropElements([1, 2, 3], function(n) {return n < 3; });
```

## Answers
```javascript
function dropElements(arr, func) {
    let newArr =[];
    //iterate through arr
    for(let i=0; i< arr.length; i++){
        //console.log(func(arr[i]))
        if(func(arr[i])){
            return newArr =arr.slice(i);
            
        }
    }return newArr;
   
}
```
