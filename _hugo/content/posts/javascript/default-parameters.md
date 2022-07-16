---
title: "JavaScript: default parameter values"
date: 2022-07-16
tags: ["javascript", "default", "parameter", "function"]
categories: ["JavaScript"]
---

```javascript
const functionName = (
  defaultParameter1 = "hello",
  defaultParameter2 = () => "world",
  defaultParameter3 = [{ otherText: "!" }]
) =>
  `${defaultParameter1} ${defaultParameter2()}${
    defaultParameter3[0].otherText
  }`;

console.log(functionName()); // hello world!
```
