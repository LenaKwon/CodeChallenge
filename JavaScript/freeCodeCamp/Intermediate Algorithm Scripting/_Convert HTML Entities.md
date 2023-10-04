# Convert HTML Entities
Convert the characters &, <, >, " (double quote), and ' (apostrophe), in a string to their corresponding HTML entities.

## Before
```javascript
function convertHTML(str) {
  return str;
}

convertHTML("Dolce & Gabbana");
```

## Answers
```javascript
let html = {
    "&" : `&amp;`,
    "<" : `&lt;`,
    ">" : `&gt;`,
    "\"" : `&quot;`,
    "\'" : `&apos;`
}

function convertHTML(str) {
   
   return str.split("")
   .map(v => html[v] || v  )// simple way
   .join("")
}
  
convertHTML("Dolce & Gabbana"); //Dolce &amp; Gabbana
convertHTML("Hamburgers < Pizza < Tacos") //Hamburgers &lt; Pizza &lt; Tacos
convertHTML("Sixty > twelve") //Sixty &gt; twelve
convertHTML('Stuff in "quotation marks"') // Stuff in &quot;quotation marks&quot;
convertHTML("Schindler's List")) //Schindler&apos;s List
convertHTML("<>") //&lt;&gt;
convertHTML("abc") //abc
```

```javascript
function convertHTML(str) {
  // Use Object Lookup to declare as many HTML entities as needed.
  const htmlEntities = {
    "&": "&amp;",
    "<": "&lt;",
    ">": "&gt;",
    '"': "&quot;",
    "'": "&apos;"
  };
  // Using a regex, replace characters with it's corresponding html entity
  return str.replace(/([&<>\"'])/g, match => htmlEntities[match]);
}

// test here
convertHTML("Dolce & Gabbana");
```
```javascript
function convertHTML(str) {
  // Split by character to avoid problems.

  var temp = str.split("");

  // Since we are only checking for a few HTML elements, use a switch

  for (var i = 0; i < temp.length; i++) {
    switch (temp[i]) {
      case "<":
        temp[i] = "&lt;";
        break;
      case "&":
        temp[i] = "&amp;";
        break;
      case ">":
        temp[i] = "&gt;";
        break;
      case '"':
        temp[i] = "&quot;";
        break;
      case "'":
        temp[i] = "&apos;";
        break;
    }
  }

  temp = temp.join("");
  return temp;
}

//test here
convertHTML("Dolce & Gabbana");
```
## Note
**first solution** using `.map(v => html[v] || v  )`  `||` </br>
**second solution** regex: `/([&<>\"'])/g` </br>
using function for second argument `match => htmlEntities[match]`

