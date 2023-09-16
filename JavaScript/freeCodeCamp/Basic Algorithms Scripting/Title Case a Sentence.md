# Title Case a Sentence
Return the provided string with the first letter of each word capitalized. Make sure the rest of the word is in lower case.

For the purpose of this exercise, you should also capitalize connecting words like `the` `and` `of`.

## Before
```javascript
function titleCase(str) {
  return str;
}

titleCase("I'm a little tea pot");
```
## Answers
```javascript
function titleCase(str) {
  return str
    .toLowerCase()
    .replace(/(^|\s)\S/g, L => L.toUpperCase);
}
titleCase("I'm a little tea pot");
```
```javascript
function titleCase(str) {
  return str
    .toLowerCase()
    .split(" ")
    .map(val=>val.replace(val.charAt[0],val.charAt[0].toUpperCase()))
    .join(" ");
    
}
titleCase("I'm a little tea pot");
```
```javascript
function titleCase(str) {
  str = str.split(" ");
  let updated = [];
  for(const st in str) {
  updated[st] = str[st][0].toUpperCase() + str[st].slice(1).toLowerCase();
  }
  return updated.join(" ");
    
}
titleCase("I'm a little tea pot");
```
