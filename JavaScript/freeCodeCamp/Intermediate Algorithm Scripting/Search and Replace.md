# Search and Replace
Perform a search and replace on the sentence using the arguments provided and return the new sentence.

First argument is the sentence to perform the search and replace on.

Second argument is the word that you will be replacing (before).

Third argument is what you will be replacing the second argument with (after).

Note: Preserve the case of the first character in the original word when you are replacing it. 
For example if you mean to replace the word Book with the word dog, it should be replaced as Dog

## Before
```javascript
function myReplace(str, before, after) {
  return str;
}

myReplace("A quick brown fox jumped over the lazy dog", "jumped", "leaped");
```
## Answers
```javascript
function myReplace(str, before, after) {
  let afterFirst = after.slice(0,1);

  const newAfter = before.charCodeAt(0) < 97 
     ? after.replace(afterFirst,afterFirst.toUpperCase()) 
     : after.replace(afterFirst,afterFirst.toLowerCase());
    
    return str.replace(before,newAfter);
  
}
myReplace("A quick brown fox jumped over the lazy dog", "jumped", "leaped"); //A quick brown fox leaped over the lazy dog
myReplace("He is Sleeping on the couch", "Sleeping", "sitting") //He is Sitting on the couch
myReplace("I think we should look up there", "up", "Down") //I think we should look down there
```
