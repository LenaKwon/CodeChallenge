# Use the parseInt Function with a Radix
The `parseInt()` function parses a string and returns an integer. It takes a second argument for the radix, 
which specifies the base of the number in the string. The radix can be an integer between 2 and 36.

The function call looks like:
```
parseInt(string, radix);
```
And here's an example:
```
const a = parseInt("11", 2);
```
The radix variable says that 11 is in the binary system, or base 2. This example converts the string 11 to an integer 3.

Use parseInt() in the convertToInteger function so it converts a binary number to an integer and returns it.

# Before
```javascript
function convertToInteger(str) {
  
}

convertToInteger("10011");
```

# Answers
```javascript
function convertToInteger(str) {
  return parseInt(str,2);
}

convertToInteger("10011");
```

## Thinking 
1. Understanding Hexadecimal number<br/>
   [Understanding Hexadecimal number](https://m.blog.naver.com/PostView.naver?isHttpsRedirect=true&blogId=silverstonec&logNo=60196870427)<br/>
   [Convert haxadecimal to binary and decimal number](https://ko.wikihow.com/16%EC%A7%84%EC%88%98%EB%A5%BC-2%EC%A7%84%EC%88%98%EC%99%80-10%EC%A7%84%EC%88%98%EB%A1%9C-%EB%B3%80%ED%99%98%ED%95%98%EB%8A%94-%EB%B2%95)

2. Understanding parseInt() function<br/>
   [mdn web docs](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/parseInt)
