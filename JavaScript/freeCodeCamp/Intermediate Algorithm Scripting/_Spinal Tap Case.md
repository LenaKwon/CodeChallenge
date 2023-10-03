# Spinal Tap Case
Convert a string to spinal case. Spinal case is all-lowercase-words-joined-by-dashes.

## Before
```javascript
function spinalCase(str) {
  return str 
}

spinalCase('This Is Spinal Tap');
```
## Answers
```javascript
function spinalCase(str) {
  return str.split(/\s|_|(?=[A-Z])/).join("-").toLowerCase();
}

spinalCase('This Is Spinal Tap');
```
```javascript
function spinalCase(str) {
  // Replace low-upper case to low-space-uppercase
  // the first replace() puts a space before any encountered uppercase characters in the string str
  // so that the spaces can be replaced by dashes later on.
  str = str.replace(/([a-z])([A-Z])/g, "$1 $2"); 
  // Split on whitespace and underscores and join with dash
  return str
    .toLowerCase()
    .split(/(?:_| )+/)
    .join("-");
}

// test here
spinalCase("This Is Spinal Tap");
```
## Need to Know
`(?: pattern)` group search regex </br>
`?=` lookahead  </br>
`?<=`lookbackbehind </br>
`?!` negative lookahead  </br>
`?<!` negative lookbehind </br>
