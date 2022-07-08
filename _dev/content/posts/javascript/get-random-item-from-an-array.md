---
title: "Get Random Item From an Array"
date: 2022-07-08
tags: ["javascript", "javascript tips", "javascript tricks", "random", "array"]
categories: ["JavaScript"]
---

```javascript
var array = [1, 2, 3];
var array2 = [4, 5, 6];

const randomArray = (arr) => {
  return arr[Math.floor(Math.random() * arr.length)];
};

randomArray(array); // 1 -> 3
// randomArray([...array, ...array2]); // 1 -> 6
```
