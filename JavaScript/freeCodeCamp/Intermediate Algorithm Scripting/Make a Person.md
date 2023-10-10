## Make a Person
Fill in the object constructor with the following methods below:
```javascript
getFirstName()
getLastName()
getFullName()
setFirstName(first)
setLastName(last)
setFullName(first, last)
```
Run the tests to see the expected output for each method. These methods must be the only available means of interacting with the object. 
Each test will declare a new `Person` instance as new `Person('Bob', 'Ross')`.

## Before
```javascript
const Person = function(first, last) {
  this.getFullName = function() {
    return "";
  };
  return "";
};
```
## Answers
```javascript
const Person = function(first, last) {
  this.getFullName = function() {
    return "";
  };
  return "";
};
```
