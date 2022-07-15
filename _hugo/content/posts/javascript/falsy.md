---
title: "JavaScript: a falsy value"
date: 2022-07-15
tags: ["javascript", "falsy value", "falsey value"]
categories: ["JavaScript"]
canonicalURL: "https://developer.mozilla.org/en-US/docs/Glossary/Falsy"
ShowCanonicalLink: true
---

### List of falsy values

- `false`
- `0`
- `-0`
- `0n`
- `""`, `''`, ` `` ` — Empty string value.
- `null`
- `undefined`
- `NaN` — not a number.
- `document.all`

### Check falsy value is `false`

- Boolean() method:

```javascript
for (const item of [false, 0, -0, 0n, "", ``, null, undefined, document.all]) {
  console.log(`${item} is ${Boolean(item)}`);
}
```

- NOT (`!`) operator method:

```javascript
for (const item of [false, 0, -0, 0n, "", ``, null, undefined, document.all]) {
  if (!item) {
    console.log(`${item} is ${!!item}`);
  }
}
```
