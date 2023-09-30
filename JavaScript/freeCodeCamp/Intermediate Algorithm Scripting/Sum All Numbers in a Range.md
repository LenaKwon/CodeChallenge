# Sum All Numbers in a Range
We'll pass you an array of two numbers. Return the sum of those two numbers plus the sum of all the numbers between them. 
The lowest number will not always come first.

For example, `sumAll([4,1])` should return `10` because sum of all the numbers between `1` and `4` (both inclusive) is `10`.

## Before
```javascript
function sumAll(arr) {
  return 1;
}

sumAll([1, 4]);
```
## Answers
```javascript
function sumAll(arr) {
 const range = arr.sort((a,b)=>a-b);
 const newArr= new Array(range[1]-range[0]+1);
 for(let i= range[0]; i<= range[1]; i++){ newArr.push(i)}
 return newArr.reduce((sum,a)=>(sum = sum + a));
}

sumAll([1, 4]);
```
구지 배열까지 만들 필요가 없는 min,max 를 이용해서 += 하는 아래 코드가 더 간단. 
```javascript
function sumAll(arr) {
  let sumBetween = 0;
  for (let i = Math.min(...arr); i <= Math.max(...arr); i++) {
    sumBetween += i;
  }
  return sumBetween;
}

sumAll([1, 4]);
```
