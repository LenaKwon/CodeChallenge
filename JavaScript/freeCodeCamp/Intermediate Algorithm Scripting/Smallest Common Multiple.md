# Smallest Common Multiple
Find the smallest common multiple of the provided parameters that can be evenly divided by both, as well as by all sequential numbers in the range between these parameters.

The range will be an array of two numbers that will not necessarily be in numerical order.

For example, if given 1 and 3, find the smallest common multiple of both 1 and 3 that is also evenly divisible by all numbers between 1 and 3. The answer here would be 6.

## Before
```javascript
function smallestCommons(arr) {
  return arr;
}

smallestCommons([1,5]);
```
## Answers
```javascript
function smallestCommons(arr) {
  let [min,max] = arr.sort((a,b)=>a-b);
  let length = max - min +1;
 
  let upperBound = 1; 
  for(let i = min; i <= max; i += min){
    upperBound *= i;
  }
  
  //highestmultiple
  for(let h=max; h<=upperBound; h +=max){
    let divisorCount =0;
    for(let i =0; i<=max; i++){
      if(h%i ===0){
        divisorCount += 1;
      }
    }
    if (divisorCount === length ){
      return h;
    }
  }
}

smallestCommons([1,5]); //60
smallestCommons([5, 1]) //60
smallestCommons([2, 10]) //2520
```

## Other solutions
[freeCodecamp Guide](https://forum.freecodecamp.org/t/freecodecamp-challenge-guide-smallest-common-multiple/16075)

