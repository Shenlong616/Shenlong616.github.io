---
title: "JavaScript: get a random element from an Array"
date: 2022-07-08
tags: ["javascript", "javascript snippets", "random", "array", "element"]
categories: ["JavaScript"]
---

```javascript
var Array1 = [1, 2, 3];
var Array2 = [4, 5, 6];

const randomArray = (parameter) => {
  return parameter[Math.floor(Math.random() * parameter.length)];
};

console.log(randomArray(Array1)); // 1, 2 or 3
console.log(randomArray([...Array1, ...Array2])); // 1, 2, 3, 4, 5 or 6
```
