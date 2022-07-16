---
title: "JavaScript: get a random item from an Array"
date: 2022-07-08
tags: ["javascript", "javascript snippets", "random", "array"]
categories: ["JavaScript"]
---

```javascript
var array = [1, 2, 3];
var array2 = [4, 5, 6];

const randomArray = (arr) => {
  return arr[Math.floor(Math.random() * arr.length)];
};

console.log(randomArray(array)); // 1, 2 or 3
console.log(randomArray([...array, ...array2])); // 1, 2, 3, 4, 5 or 6
```
