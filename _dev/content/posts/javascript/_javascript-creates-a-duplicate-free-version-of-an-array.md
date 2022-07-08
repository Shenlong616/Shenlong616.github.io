---
title: "JavaScript: creates a duplicate-free version of an Array"
date: 2022-07-08
tags: ["javascript", "javascript snippets", "duplicate-free", "unique", "array"]
categories: ["JavaScript"]
draft: true
---

https://viblo.asia/p/javascript-unique-array-bai-toan-quoc-dan-924lJGdW5PM

### Set()

```javascript
var array = [1, 2, 2, 3, 3, 3, 4, 4, 4, 4, 5, 5, 5, 5, 5];
var array2 = [...new Set(array)];

console.log(array2); // [1, 2, 3, 4, 5]
```

### Set() and map()

```javascript
const People = [
  {
    name: "John",
    age: 21,
  },
  {
    name: "Arthur",
    age: 22,
  },
  {
    name: "John",
    age: 23,
  },
];

const uniquePeopleName = [...new Set(People.map((element) => element.name))];
const uniquePeopleAge = [...new Set(People.map((element) => element.age))];

console.log(uniquePersonName);
```
