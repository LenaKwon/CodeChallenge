# Truncate a String
Truncate a string (first argument) if it is longer than the given maximum string length (second argument). 
Return the truncated string with a `...` ending.

## Before
```javascript
function truncateString(str, num) {
  return str;
}

truncateString("A-tisket a-tasket A green and yellow basket", 8);
```
## Answers
```javascript
function truncateString(str, num) {
 retrun (str.length > num ? str.slice(0,num)+"..." :str.slice(0,num));
}

truncateString("A-tisket a-tasket A green and yellow basket", 8);
```
