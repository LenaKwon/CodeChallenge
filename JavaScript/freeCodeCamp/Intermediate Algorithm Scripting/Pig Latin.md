# Pig Latin
Pig Latin is a way of altering English Words. The rules are as follows:

- If a word begins with a consonant, take the first consonant or consonant cluster, move it to the end of the word, and add `ay` to it.

- If a word begins with a vowel, just add `way` at the end.

Translate the provided string to Pig Latin. Input strings are guaranteed to be English words in all lowercase.

## Before
```javascript
function translatePigLatin(str) {
  return str;
}

translatePigLatin("consonant");
```
## Answers
```javascript

 function translatePigLatin(str) {
  let regex = /^[^aeiou]+/;
  let myConsnant = str.match(regex);
  return myConsnant !== null ? 
    str
      .replace(regex,"")
      .concat(myConsnant)
      .concat("ay")
   : str.concat("way");
}

translatePigLatin("consonant");
```
## note
result will be different with () paranthesis here as we need to concat() strings behind
 `let regex = /^[^aeiou]+/;`
 console.log(translatePigLatin("consonant")); //onsonantc,cay
 `let regex = /(^[^aeiou]+)/;`
 console.log(translatePigLatin("consonant")); //onsonantcay
