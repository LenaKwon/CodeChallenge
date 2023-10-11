Roman Numeral Converter
Convert the given number into a roman numeral.

Roman numerals	Arabic numerals </br>
<img width="295" alt="Screenshot 2023-10-11 at 2 37 10 PM" src="https://github.com/LenaKwon/CodeChallenge/assets/37726487/32244434-2056-4733-9f3c-d0ef122db0fc"></br>

All roman numerals answers should be provided in upper-case.</br>

## Before
```javascript
function convertToRoman(num) {
 return num;
}

convertToRoman(36);
```
## Answers
```javascript
let lookup ={
    M:	1000,
    CM:	900,
    D:	500,
    CD:	400,
    C:	100,
    XC:	90,
    L:	50,
    XL:	40,
    X:	10,
    IX:	9,
    V:	5,
    IV:	4,
    I:	1
}
 
function convertToRoman (num){
    let roman ='';

    for(let i in lookup){
        while(num >= lookup[i]){
            roman += i;
            console.log(roman)
            num -= lookup[i]
            console.log(num)
        }
    }
    return roman;
}

convertToRoman(36);
```
