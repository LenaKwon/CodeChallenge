# Find the Longest Word in a String
Return the length of the longest word in the provided sentence.

Your response should be a number.

## Before
```javascript
function findLongestWordLength(str) {
  return str.length;
}

findLongestWordLength("The quick brown fox jumped over the lazy dog");
```
## Answers
```javascript
function findLongestWordLength(str) {
    str= str.split(" ");
    let strlength =[];
    for(let i=0 ; i < str.length; i++){
        let dividedstr = str[i].split("");
        strlength.push(dividedstr.length)
    }
    return Math.max(...strlength);
}
findLongestWordLength("The quick brown fox jumped over the lazy dog");
```
## short code
```javascript
function findLongestWordLength(str) {
  return Math.max(...str.split(" ").map(word => word.length));
}
```
