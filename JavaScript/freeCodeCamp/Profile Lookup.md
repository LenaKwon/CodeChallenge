# Profile Lookup

We have an array of objects representing different people in our contacts lists.

A `lookUpProfile` function that takes `name` and a property (`prop`) as arguments has been pre-written for you.

The function should check if `name` is an actual contact's `firstName` and the given property (`prop`) is a property of that contact.

If both are true, then return the "value" of that property.

If `name` does not correspond to any contacts then return the string `No such contact`.

If `prop` does not correspond to any valid properties of a contact found to match `name` then return the string `No such property`.

## before
```javascript

// Setup
const contacts = [
  {
    firstName: "Akira",
    lastName: "Laine",
    number: "0543236543",
    likes: ["Pizza", "Coding", "Brownie Points"],
  },
  {
    firstName: "Harry",
    lastName: "Potter",
    number: "0994372684",
    likes: ["Hogwarts", "Magic", "Hagrid"],
  },
  {
    firstName: "Sherlock",
    lastName: "Holmes",
    number: "0487345643",
    likes: ["Intriguing Cases", "Violin"],
  },
  {
    firstName: "Kristian",
    lastName: "Vos",
    number: "unknown",
    likes: ["JavaScript", "Gaming", "Foxes"],
  },
];

function lookUpProfile(name, prop) {
  // Only change code below this line

  // Only change code above this line
}

lookUpProfile("Akira", "likes");

```

## answers

```javascript

//first trial- incorrect

function lookUpProfile(name, prop) {
  // Only change code below this line

function lookUpProfile(name, prop) {
  // Only change code below this line
  
 for (let i = 0; i < contacts.length; i++) {

    if(name === contacts[i].firstName && contacts[i].hasOwnProperty(prop)){
          return contacts[i][prop];
       }else if(!contacts.hasOwnProperty(name)){
          return "No such Contact";
       }else if(!contacts[i].hasOwnProperty(prop)){
          return "No such property";
       }
 }

```
```javascript

//second trial- incorrect

for (let i = 0; i < contacts.length; i++) {

    if(name === contacts[i].firstName && contacts[i].hasOwnProperty(prop)){
          return contacts[i][prop];
          if(!contacts.hasOwnProperty(name)){
            return "No such Contact";
            }else{
              return "No such property";
            }    
       }
 }
```
```javascript

//third trial- correct!

function lookUpProfile(name, prop) {
  // Only change code below this line
  
 for (let i = 0; i < contacts.length; i++) {

    if(name === contacts[i].firstName){
        if(contacts[i].hasOwnProperty(prop)){
          return contacts[i][prop];
       }else{
         return "No such property";
       }
    }
 }
 return "No such contact"

```

## thinking 
1. String of "No such Contact" should be returned after finishing the loop in the 'contacts'. 
If the return statement is located `in the for loop`, then looping is stopped at the point before looping the whole contacts.
2. Imagin the looping process and minimise unnecessary coding and simplify it rather than making code for the each condition.
