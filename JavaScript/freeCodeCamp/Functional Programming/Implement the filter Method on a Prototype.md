# Implement the filter Method on a Prototype
You might learn a lot about the filter method if you implement your own version of it. It is recommended you use a `for` loop or `Array.prototype.forEach()`.

Write your own `Array.prototype.myFilter()`, which should behave exactly like `Array.prototype.filter()`. You should not use the built-in filter method. 
The Array instance can be accessed in the `myFilter` method using this.

## Before
```javascript
Array.prototype.myFilter = function(callback) {
  const newArray = [];
  // Only change code below this line

  // Only change code above this line
  return newArray;
};
```
## Answers
```javascript
Array.prototype.myFilter = function (callback) {
  const newArray = [];
  // Only change code below this line
  for (let i = 0; i < this.length; i++) {
      if (callback(this[i], i, this) == true) {
      newArray.push(this[i]);
    }
  }
  // Only change code above this line
  return newArray;
};
  // Only change code above this line
  return newArray;
};
```
```javascript
// Only change code below this line
const filteredList = watchList
  .filter(({ imdbRating }) => imdbRating >= 8.0)
  .map(({ Title: title, imdbRating: rating }) => ({ title, rating }));
// Only change code above this line

console.log(filteredList);
```
```javascript
const filteredList = watchList
  .filter(movie => {
    // return true it will keep the item
    // return false it will reject the item
    return parseFloat(movie.imdbRating) >= 8.0;
  })
  .map(movie => {
    return {
      title: movie.Title,
      rating: movie.imdbRating
    };
  });
```
