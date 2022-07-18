---
title: "JavaScript: custom CSS styles"
date: 2022-07-18
tags: ["javascript", "CSS", "javascript snippets", "property"]
categories: ["JavaScript"]
---

- `cssText` property

```javascript
document.querySelectorAll(
  ".logo"
)[0].childNodes[0].style.cssText = `color: var(--color_5) !important;`;
```
