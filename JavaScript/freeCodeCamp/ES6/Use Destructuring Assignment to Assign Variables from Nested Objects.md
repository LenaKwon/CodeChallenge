# Use Destructuring Assignment to Assign Variables from Nested Objects
You can use the same principles from the previous two lessons to destructure values from nested objects.

Using an object similar to previous examples:

```javascript
const user = {
  johnDoe: { 
    age: 34,
    email: 'johnDoe@freeCodeCamp.com'
  }
};
```
Here's how to extract the values of object properties and assign them to variables with the same name:
```javascript
const { johnDoe: { age, email }} = user;
```

And here's how you can assign an object properties' values to variables with different names:
```javascript
const { johnDoe: { age: userAge, email: userEmail }} = user;
```

Replace the two assignments with an equivalent destructuring assignment. 
It should still assign the variables `lowToday` and `highToday` the values of `today.low` and `today.high` from the `LOCAL_FORECAST` object.

## Before
```javascript
const LOCAL_FORECAST = {
  yesterday: { low: 61, high: 75 },
  today: { low: 64, high: 77 },
  tomorrow: { low: 68, high: 80 }
};

// Only change code below this line
  
const lowToday = LOCAL_FORECAST.today.low;
const highToday = LOCAL_FORECAST.today.high;

// Only change code above this line
```

## Answers
```javascript
const LOCAL_FORECAST = {
  yesterday: { low: 61, high: 75 },
  today: { low: 64, high: 77 },
  tomorrow: { low: 68, high: 80 }
};

// Only change code below this line

const {today :{ low : today.low, high : today.high  } =LOCAL_FORECAST;


// Only change code above this line
```

## Caution
Don't forget the colone between before inner brace.
