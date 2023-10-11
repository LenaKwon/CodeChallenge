# Caesars Cipher
One of the simplest and most widely known ciphers is a Caesar cipher, also known as a shift cipher. In a shift cipher the meanings of the letters are shifted by some set amount.

A common modern use is the ROT13 cipher, where the values of the letters are shifted by 13 places. Thus A ↔ N, B ↔ O and so on.

Write a function which takes a ROT13 encoded string as input and returns a decoded string.

All letters will be uppercase. Do not transform any non-alphabetic character (i.e. spaces, punctuation), but do pass them on.

## Before
```javascript
function rot13(str) {
  return str;
}

rot13("SERR PBQR PNZC");
```
## After
```javascript
function rot13(str) {
    let n = str.length;
    let cipher =[];
    let msg =[];

    for(let j=0; j< n; j++){
        cipher.push(str.charCodeAt(j))
    }

    let arr =[...cipher];
    for(let i =0; i < n; i++){
        //if (48 <= cipher[i] && cipher[i] <= 57 ){cipher[i] = cipher[i]+13}
        if ( 65 <= cipher[i] && cipher[i] <= 77 ){ arr[i]=cipher[i]+13}
        if (78 <= cipher[i] && cipher[i] <= 90 ){arr[i] = cipher[i]-13}
    }

    for(let z=0; z < n; z++){
        msg.push(String.fromCharCode(arr[z]))
    }

    return msg.join('');
}
```

