---
title: "JavaScript: empty an Array?"
date: 2022-07-18
tags: ["javascript", "empty", "array", "javascript snippets", "method"]
categories: ["JavaScript"]
---

### Declare

```javascript
A = [];
```

### Set

- `splice()` method

```javascript
B = [1, 2, 3]; // [1, 2, 3]

B.splice(0, B.length);
console.log(B); // []
```
