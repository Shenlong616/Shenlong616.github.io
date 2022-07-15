---
title: "JavaScript: callback Function"
date: 2022-07-15
tags: ["javascript", "callback", "function"]
categories: ["JavaScript"]
---

```javascript
let fullText = "";

const myArray1 = [{ helloText: ["hello"] }];
const myArray2 = ["world"];
const myArray3 = [
  {
    function(parameter) {
      fullText += `${parameter} `;
    },
  },
];

[...myArray1[0].helloText, ...myArray2, "1998"].map((value) => {
  myArray3[0].function(value);
});

console.log(`${fullText.trim()}!`); // hello world 1998!
console.log(fullText.length); // 17
```
