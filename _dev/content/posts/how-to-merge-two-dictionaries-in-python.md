---
title: "How to merge two dictionaries in Python"
date: 2022-07-05
# description: ""
tags: ["python", "python2", "python3", "python tricks", "merge", "dictionary"]
categories: ["Python"]
author: "Unknown"
showToc: false
---

#### Python 2.x

```Python
x = {"a": 1, "b": 2}
y = {"b": 3, "c": 4}
z = dict(x, **y)

print(z)  # {'a': 1, 'b': 3, 'c': 4}
```

#### Python 3.5+

```Python
x = {"a": 1, "b": 2}
y = {"b": 3, "c": 4}
z = {**x, **y}

print(z)  # {'a': 1, 'b': 3, 'c': 4}
```
