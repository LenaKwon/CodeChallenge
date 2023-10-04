# Missing letters
Find the missing letter in the passed letter range and return it.

If all letters are present in the range, return undefined.

## Before
```javascript
function fearNotLetter(str) {
  return str;
}

fearNotLetter("abce");
```
## Answers
```javascript
function fearNotLetter(str) {
    let start = str.charCodeAt(0);
    let end = str.charCodeAt(str.length-1);
    
    for(start; start < end; start++){
        if(str.indexOf(String.fromCharCode(start)) === -1 ) {
           return String.fromCharCode(start); 
        }    
    } 
}

fearNotLetter("abce"); //d
fearNotLetter("abcdefghjklmno") //i
fearNotLetter("stvwx") //u
fearNotLetter("abcdefghijklmnopqrstuvwxyz") //undefined
```
