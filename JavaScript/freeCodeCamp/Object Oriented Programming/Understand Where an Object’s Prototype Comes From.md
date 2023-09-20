# Understand Where an Object’s Prototype Comes From
Just like people inherit genes from their parents, an object inherits its prototype directly from the constructor function that created it. 
For example, here the Bird constructor creates the duck object:
```javascript
function Bird(name) {
  this.name = name;
}

let duck = new Bird("Donald");
```
duck inherits its prototype from the Bird constructor function. You can show this relationship with the `isPrototypeOf` method:
```javascript
Bird.prototype.isPrototypeOf(duck);
```
This would return `true`.

Use `isPrototypeOf` to check the prototype of `beagle`.

## Before
```javascript
function Dog(name) {
  this.name = name;
}

let beagle = new Dog("Snoopy");

// Only change code below this line
```
## Answers
```javascript
function Dog(name) {
  this.name = name;
}

let beagle = new Dog("Snoopy");
// Only change code below this line

Dog.prototype.isPrototypeOf(beagle);
```
