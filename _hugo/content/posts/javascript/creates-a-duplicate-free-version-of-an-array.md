---
title: "JavaScript: creates a duplicate-free version of an Array"
date: 2022-07-08
tags:
  [
    "javascript",
    "javascript snippets",
    "duplicate-free",
    "unique",
    "array",
    "method",
  ]
categories: ["JavaScript"]
---

- `Set()` method

```javascript
console.log([...new Set([1, 2, 2, 3, 3, 3])]); // [1, 2, 3]
```
