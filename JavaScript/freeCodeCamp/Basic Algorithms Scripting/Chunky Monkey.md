# Chunky Monkey
Write a function that splits an array (first argument) into groups the length of size (second argument) 
and returns them as a two-dimensional array.

## Before
```javascript
function chunkArrayInGroups(arr, size) {
  return arr;
}

chunkArrayInGroups(["a", "b", "c", "d"], 2);
```
## Answers
```javascript
function chunkArrayInGroups(arr, size) {
  const newArr = [];
  let i = 0;
  while ( i < arr.length ) {
    newArr.push(arr.slice(i,i+size));
    i += size;
  }
}
chunkArrayInGroups(["a", "b", "c", "d"], 2);
```
```javascript
function chunkArrayInGroups(arr, size) {
    const newArr = [];
    while (arr.length > 0) {
    newArr.push(arr.splice(0,size));
  }
}
chunkArrayInGroups(["a", "b", "c", "d"], 2);
```
