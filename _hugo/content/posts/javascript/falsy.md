---
title: "JavaScript: falsy values"
date: 2022-07-15
tags: ["javascript", "falsy value", "falsey value"]
categories: ["JavaScript"]
---

### List of falsy values

- `false`
- `0`
- `-0`
- `0n`
- `""`, `''`, ` `` ` — empty string value.
- `null` — the absence of any value.
- `undefined` — the primitive value.
- `NaN` — not a number.
- `document.all`

### Check a falsy value is false

- `Boolean()` method:

```javascript
for (const item of [false, 0, "", null, undefined, document.all]) {
  console.log(`${item} is ${Boolean(item)}`);
}
```

- NOT (`!`) operator method:

```javascript
for (const item of [false, 0, "", null, undefined, document.all]) {
  if (!item) {
    console.log(`${item} is ${!!item}`);
  }
}
```
