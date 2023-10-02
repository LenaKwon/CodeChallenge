# Wherefore art thou
Make a function that looks through an array of objects (first argument) and returns an array of all objects that have matching name and value pairs (second argument). 
Each name and value pair of the source object has to be present in the object from the collection if it is to be included in the returned array.

For example, if the first argument is `[{ first: "Romeo", last: "Montague" }, { first: "Mercutio", last: null }, { first: "Tybalt", last: "Capulet" }]`, 
and the second argument is `{ last: "Capulet" }`, then you must return the third object from the array (the first argument), because it contains the name and its value, 
that was passed on as the second argument.

## Before
```javascript
function whatIsInAName(collection, source) {

}

whatIsInAName([{ first: "Romeo", last: "Montague" }, { first: "Mercutio", last: null }, { first: "Tybalt", last: "Capulet" }], { last: "Capulet" });
```
## Answers
```javascript
//double forloop, using keys from `for/in loop`
function whatIsInAName(collection, source) {
    const collectMatches =[];

    for(let i=0; i < collection.length; i++){
        let isMatch = true; // 이걸 forloop 밖에 정의했더니 결과값이 []. 변수의 위치를 잘 파악하자.
        for(const key in source){
            if(collection[i][key] !== source[key]){
               isMatch = false;
            }
        }
        if (isMatch){ collectMatches.push(collection[i])}// 이 코드는 forloop 밖에 있어야 됨. 조건이 true 인 경우만 push
    }
    return collectMatches;
}


whatIsInAName([{ first: "Romeo", last: "Montague" }, { first: "Mercutio", last: null }, { first: "Tybalt", last: "Capulet" }], { last: "Capulet" });
```
```javascript
// using filter(), for loop and Object.keys()

function whatIsInAName(collection, source) {
    const sourceKey = Object.keys(source);
    return collection.filter(obj =>{
        for(let i =0; i < sourceKey.length; i++){
            if(obj[sourceKey[i]]!==source[sourceKey[i]]){
                return false;
            }
        }return true;
    })  
}
```
```javascript
// using hight order function only - filter(), every() and using Object.keys() for keys

function whatIsInAName(collection,source){
   const sourceKey = Object.keys(source);
   return collection.filter( obj => sourceKey.every(key => obj[key] === source[key] ) )
}

```
