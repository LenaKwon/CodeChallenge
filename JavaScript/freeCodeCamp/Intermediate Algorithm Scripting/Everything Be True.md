# Everything Be True
Check if the predicate (second argument) is truthy on all elements of a collection (first argument).

In other words, you are given an array collection of objects. The predicate pre will be an object property and you need to return true if its value is truthy. Otherwise, return false.

In JavaScript, truthy values are values that translate to true when evaluated in a Boolean context.

Remember, you can access object properties through either dot notation or [] notation.

## Before
```javascript
function truthCheck(collection, pre) {
  return pre;
}

truthCheck([{name: "Quincy", role: "Founder", isBot: false}, {name: "Naomi", role: "", isBot: false}, {name: "Camperbot", role: "Bot", isBot: true}], "isBot");
```

## Other Solution
```javascript
function truthCheck(collection, pre) {
  // Is everyone being true?
  return collection.every(obj => obj[pre]);
}

truthCheck([{ name: "Quincy", role: "Founder", isBot: false }, { name: "Naomi", role: "", isBot: false }, { name: "Camperbot", role: "Bot", isBot: true }], "isBot");
```
### code explanation
For every object in the collection array, check the truthiness of object’s property passed in pre parameter
Array.prototype.every method internally checks if the value returned from the callback is truthy.
Return true if it passes for every object. Otherwise, return false.
</br>
</br>
```javascript
function truthCheck(collection, pre) {
  return collection.every(function (element) {
    return element.hasOwnProperty(pre) && Boolean(element[pre]);
  });
}

truthCheck([{ name: "Quincy", role: "Founder", isBot: false }, { name: "Naomi", role: "", isBot: false }, { name: "Camperbot", role: "Bot", isBot: true }], "isBot");
```

```javascript
function truthCheck(collection, pre) {
  // Create a counter to check how many are true.
  let counter = 0;
  // Check for each object
  for (let c in collection) {
    // If it is has property and value is truthy
    if (collection[c].hasOwnProperty(pre) && Boolean(collection[c][pre])) {
      counter++;
    }
  }
  // Outside the loop, check to see if we got true for all of them and return true or false
  return counter == collection.length;
}

truthCheck([{ name: "Quincy", role: "Founder", isBot: false }, { name: "Naomi", role: "", isBot: false }, { name: "Camperbot", role: "Bot", isBot: true }], "isBot");

```
## Relevant links
[hasOwnProperty](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/hasOwnProperty)</br>
[Boolean](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Boolean) </br>

## Incomplete Answer
```javascript
// This code is incomplete..'number' part hasn't been solved..
// This code is using ineffective way.. don't do this next time.

function truthCheck(collection, pre) {
    let newArr =[];
    for(let i=0; i < collection.length; i++){
        newArr.push (collection[i][pre]); 
    }
   
    if(pre == 'isBot'){
            return newArr.every(v=> v == true);
    }else if(pre == 'name'){
            return newArr.every(v=> typeof v == `string`);
    }else if(pre == 'role'){
            return newArr.every(v=> v !== "");
    }else if(pre == 'caught'){
            return newArr.every(v=> v !== 0);
    }else if(pre == 'number'){
            return newArr.every(v => v == Object.is(v,NaN)) 
    }else if(pre == 'username'){
            return newArr.every(v=> v !== undefined);
    }else if(pre == 'users'){
            return newArr.every(v=> v !== "");
    }else if(pre == 'data'){
            return newArr.every(v=> typeof v == 'object');
    }else if (pre == 'id'){
            return newArr.every(v=> v !== null);
    }     
}
```
