---
title: "Function argument unpacking in Python"
date: 2022-07-05
# description: ""
tags: ["python", "python tips", "function", "argument"]
categories: ["Python"]
author: "Unknown"
draft: true
---

```Python
def myfunc(x, y, z):
    print(x, y, z)

tuple_vec = (1, 0, 1)
dict_vec = {"x": 1, "y": 0, "z": 1}

myfunc(*tuple_vec)  # 1 0 1
myfunc(**dict_vec)  # 1 0 1
```
