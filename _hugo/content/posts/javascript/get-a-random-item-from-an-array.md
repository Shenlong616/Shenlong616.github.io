---
title: "JavaScript: get a random item from an Array"
date: 2022-07-08
tags: ["javascript", "javascript snippets", "random", "array"]
categories: ["JavaScript"]
---

```javascript
var myArray = [1, 2, 3];
var myArray2 = [4, 5, 6];

const randomArray = (parameter) => {
  return parameter[Math.floor(Math.random() * parameter.length)];
};

console.log(randomArray(myArray)); // 1, 2 or 3
console.log(randomArray([...myArray, ...myArray2])); // 1, 2, 3, 4, 5 or 6
```
