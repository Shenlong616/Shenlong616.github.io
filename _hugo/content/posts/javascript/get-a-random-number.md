---
title: "JavaScript: get a random Number"
date: 2022-07-16
tags: ["javascript", "random", "number", "javascript snippets", "integer"]
categories: ["JavaScript"]
---

### Positive integer

- 0 to 2

```javascript
console.log(Math.floor(Math.random() * 3)); // 0, 1 or 2
```

- 1 to 3

```javascript
console.log(Math.floor(Math.random() * 3) + 1); // 1, 2 or 3
```

- etc.

### Negative integer

- -3 to -1

```javascript
console.log(Math.floor(Math.random() * -3)); // -3, -2 or -1
```

- -4 to -2

```javascript
console.log(Math.floor(Math.random() * -3) - 1); // -4, -3 or -2
```

- etc.
