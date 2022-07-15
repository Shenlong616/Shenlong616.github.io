---
title: "JavaScript: a falsy value"
date: 2022-07-15
tags: ["javascript", "falsy value", "falsey value"]
categories: ["JavaScript"]
canonicalURL: "https://developer.mozilla.org/en-US/docs/Glossary/Falsy"
ShowCanonicalLink: true
---

| Value              | Description                                                                                                                                           |
| ------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------- |
| `false`            | The keyword `false`.                                                                                                                                  |
| `0`                | The `Number` zero (so, also `0.0`, etc., and `0x0`).                                                                                                  |
| `-0`               | The `Number` negative zero (so, also `-0.0`, etc., and `-0x0`).                                                                                       |
| `0n`               | The `BigInt` zero (so, also `0x0n`). Note that there is no `BigInt` negative zero — the negation of `0n` is `0n`.                                     |
| `""`, `''`, ` `` ` | Empty string value.                                                                                                                                   |
| null               | The absence of any value.                                                                                                                             |
| undefined          | The primitive value.                                                                                                                                  |
| NaN                | Not a number.                                                                                                                                         |
| `document.all`     | Objects are falsy if and only if they have the `IsHTMLDDA` internal slot. That slot only exists in `document.all` and cannot be set using JavaScript. |
