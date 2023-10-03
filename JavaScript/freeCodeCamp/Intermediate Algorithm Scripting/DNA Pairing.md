# DNA Pairing
Pairs of DNA strands consist of nucleobase pairs. Base pairs are represented by the characters AT and CG, 
which form building blocks of the DNA double helix.

The DNA strand is missing the pairing element. Write a function to match the missing base pairs for the provided DNA strand. 
For each character in the provided string, find the base pair character. Return the results as a 2d array.

For example, for the input `GCG`, return `[["G", "C"], ["C","G"], ["G", "C"]]`

The character and its pair are paired up in an array, and all the arrays are grouped into one encapsulating array.

## Before
```javascript
function pairElement(str) {
  return str;
}

pairElement("GCG");
```
## Answers
```javascript
let basePair = {
    A : ["A","T"],
    T : ["T","A"],
    C : ["C","G"],
    G : ["G","C"]
}
function pairElement(str) {
    const newStr = str.split("");
    let newArr = [];
   
    for(let i=0; i<newStr.length; i++){
        for(let x in basePair){
            if(newStr[i]=== x){
                newArr.push(basePair[x]);     
            }
        }
    }return newArr;    
}

pairElement("ATCGA") //[["A","T"],["T","A"],["C","G"],["G","C"],["A","T"]]
pairElement("TTGAG") //[["T","A"],["T","A"],["G","C"],["A","T"],["G","C"]]
pairElement("CTCTA") //[["C","G"],["T","A"],["C","G"],["T","A"],["A","T"]]
```
```javascript
//similar to mine but much simple code

function pairElement(str) {
  // create object for pair lookup
  const pairs = {
    A: "T",
    T: "A",
    C: "G",
    G: "C"
  };

  // map character to array of character and matching pair
  return str
    .split("")
    .map(x => [x, pairs[x]]);
}

// test here
pairElement("GCG");
```
```javascript
//using swith()

function pairElement(str) {
  // Function to match each character with the base pair
  const matchWithBasePair = function(char) {
    switch (char) {
      case "A":
        return ["A", "T"];
      case "T":
        return ["T", "A"];
      case "C":
        return ["C", "G"];
      case "G":
        return ["G", "C"];
    }
  };

  // Find pair for every character in the string
  const pairs = [];
  for (let i = 0; i < str.length; i++) {
    pairs.push(matchWithBasePair(str[i]));
  }

  return pairs;
}

// test here
pairElement("GCG");
```
