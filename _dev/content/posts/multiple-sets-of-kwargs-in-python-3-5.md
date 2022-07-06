---
title: "Multiple sets of kwargs in Python 3.5+"
date: 2022-07-05
description: "Python 3.5+ allows passing multiple sets of keyword arguments (kwargs) to a function within a single call"
tags: ["python", "python3", "python tricks", "kwargs"]
categories: ["Python"]
author: "Unknown"
draft: true
---

#### using the `**` syntax

```Python
def process_data(a, b, c, d):
    print(a, b, c, d)

x = {"a": 1, "b": 2}
y = {"c": 3, "d": 4}

process_data(**x, **y)  # 1 2 3 4
process_data(**x, c=23, d=42)  # 1 2 23 42
```
