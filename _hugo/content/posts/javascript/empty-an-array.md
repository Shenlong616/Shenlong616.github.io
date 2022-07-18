---
title: "JavaScript: empty an Array"
date: 2022-07-18
tags: ["javascript", "empty", "array", "javascript snippets", "method"]
categories: ["JavaScript"]
---

- `[]`

```javascript
A = []; // []
```

- `splice()` method

```javascript
A = [1, 2, 3]; // [1, 2, 3]

A.splice(0, A.length);
console.log(A); // []
```
