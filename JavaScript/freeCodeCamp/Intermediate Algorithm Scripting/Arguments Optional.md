# Arguments Optional
Create a function that sums two arguments together. If only one argument is provided, then return a function that expects one argument and returns the sum.

For example, `addTogether(2, 3)` should return `5`, and `addTogether(2)` should return a `function`.

Calling this returned function with a single argument will then return the sum:
```javascript
var sumTwoAnd = addTogether(2);
```
`sumTwoAnd(3)` returns `5`.

If either argument isn't a valid number, return `undefined`.

## Before
```javascript
function addTogether() {
  return false;
}

addTogether(2,3);
```
## Answers
```javascript
function addTogether() {
   const [a,b] = arguments;
   if( typeof (a) === 'number'){
      if(typeof (b) === 'number'){ return a + b; }
      if(arguments.length ===1){ return (b)=> addTogether(a,b) }
   }
}

addTogether(2,3);
```
```javascript
function addTogether() {
  const [first, second] = arguments;

  function addSecond(second) {
    if (typeof (second) === "number") return first + second;
  }

  if (typeof (first) === "number") {
    if (arguments.length === 1) return addSecond;
    if (arguments.length === 2) return addSecond(second);
  }
}
```
```javascript
function addTogether() {
  const [first, second] = arguments;
  // First argument is not a number
  if (typeof(first) !== "number") {
    return undefined;
  }
  // First argument is a number
  //  and second argument is not defined
  else if (arguments.length === 1) {
    function addSecond(second) {
      // New argument is not a number
      if (typeof(second) !== "number") {
        return undefined;
      }
      // New argument is a number
      else {
        return first + second;
      }
    }
    // Note: returning a *function*
    return addSecond;
  }
  // First argument is a number
  //  and second argument is not a number
  else if (typeof(second) !== "number") {
    return undefined;
  }
  // First argument is a number
  //  and second argument is a number
  else {
    return first + second;
  }
}
```
