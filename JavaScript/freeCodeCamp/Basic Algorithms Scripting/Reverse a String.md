# Reverse a String
Reverse the provided string and return the reversed string.

For example, "hello" should become "olleh".

## Before
```javascrip
function reverseString(str) {
  return str;
}

reverseString("hello");
```
## Before
```javascrip
function reverseString(str) {
  let reversed ="";
  for(let i= str.length-1 ; i >=0  ; i--){
    reversed = str[i];
  }
  return reversed;
}

reverseString("hello");
```
