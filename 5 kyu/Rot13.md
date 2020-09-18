# Rot13

## Problem
ROT13 is a simple letter substitution cipher that replaces a letter with the letter 13 letters after it in the alphabet. ROT13 is an example of the Caesar cipher.

Create a function that takes a string and returns the string ciphered with Rot13. If there are numbers or special characters included in the string, they should be returned as they are. Only letters from the latin/english alphabet should be shifted, like in the original Rot13 "implementation".

## Solution
```javascript
const rot13 = (
  m,
  cypher = "abcdefghijklmnopqrstuvwxyzabcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZABCDEFGHIJKLMNOPQRSTUVWXYZ"
) =>
  m
    .split("")
    .reduce(
      (a, c, i) =>
        /[^a-zA-Z]+/g.test(c)
          ? (a += c)
          : (a += cypher[cypher.indexOf(m[i]) + 13]),
      ""
    );
```