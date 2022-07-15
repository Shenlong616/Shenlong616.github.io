---
title: "JavaScript: creates a duplicate-free version of an Array"
date: 2022-07-08
tags: ["javascript", "javascript snippets", "duplicate-free", "unique", "array"]
categories: ["JavaScript"]
canonicalURL: "https://viblo.asia/p/javascript-unique-array-bai-toan-quoc-dan-924lJGdW5PM"
# ShowCanonicalLink: true
---

```javascript
const array = [1, 2, 2, 3, 3, 3];

// https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set
const uniqueArray = [...new Set(array)];
console.log(uniqueArray); // [1, 2, 3]
```

```javascript
const Champions = [
  {
    name: "Yasuo",
    age: 18,
  },
  {
    name: "Zed",
    age: 19,
  },
  {
    name: "Darius",
    age: 20,
  },
  {
    name: "Yasuo",
    age: 21,
  },
  {
    name: "Kha'Zix",
    age: 21,
  },
];

// https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map
const uniqueChampionsName = [
  ...new Set(Champions.map((element) => element.name)),
];
const uniqueChampionsAge = [
  ...new Set(Champions.map((element) => element.age)),
];

console.log(uniqueChampionsName); // ['Yasuo', 'Zed', 'Darius', "Kha'Zix"]
```
