---
title: "🐍 PyTricks.py"
date: 2020-01-16
description: "List of Python tricks from Dan Bader's (realpython.com) newsletter"
tags: ["python", "python tips", "python tricks"]
categories: ["Python"]
author: "wcarhart, dbader"
canonicalURL: "https://gist.github.com/wcarhart/8d897d723ba6cd2af75115c38427e233"
ShowCanonicalLink: true
---

```python
# ===================================== #

# How to merge two dictionaries (3.5+)
x = {'a': 1, 'b': 2}
y = {'b': 3, 'c': 4}
z = {**x, **y}
print(z)
# {'c': 4, 'a': 1, 'b': 3}

# ===================================== #

# How to test flags
x, y, z = 0, 1, 0
if x == 1 or y == 1 or z == 1:
  print('passed')
if 1 in (x, y, z):
  print('passed')

# truthiness only:
if x or y or z:
  print('passed')
if any((x, y, z)):
  print('passed')

# ===================================== #

# How to sort a dictionary by value
d = {'a': 4, 'b': 3, 'c': 2, 'd': 1}
sorted(d.items(), key=lambda x: x[1])
# [('d', 1), ('c', 2), ('b', 3), ('a', 4)]

# ===================================== #

# Use get() to use default values with dictionaries
name_for_userid = {
  382: 'Alice',
  590: 'Bob',
  951: 'Dilbert'
}
def greeting(userid):
  print f"Hi {name_for_userid.get(userid, 'there')}!"
greeting(382)
# "Hi Alice!"
greeting(333333)
# "Hi there!"

# ===================================== #

# How to use namedtuples
from collections import namedtuple
Car = namedtuple('Car', 'color mileage')
my_car = Car('red', 3812.4)
my_car.color
# "red"
my_car.mileage
# 3812.4
my_car
# Car(color='red' , mileage=3812.4)

# like tuples, namedtuples are immutable
my_car.color = 'blue'
# AttributeError: "can't set attribute"

# ===================================== #

# Get the pythonic style guide, the Zen of Python (PEP 20)
import this
"""
The Zen of Python, by Tim Peters

Beautiful is better than ugly.
Explicit is better than implicit.
Simple is better than complex.
Complex is better than complicated.
Flat is better than nested.
Sparse is better than dense.
Readability counts.
Special cases aren't special enough to break the rules.
Although practicality beats purity.
Errors should never pass silently.
Unless explicitly silenced.
In the face of ambiguity, refuse the temptation to guess.
There should be one-- and preferably only one --obvious way to do it.
Although that way may not be obvious at first unless you're Dutch.
Now is better than never.
Although never is often better than *right* now.
If the implementation is hard to explain, it's a bad idea.
If the implementation is easy to explain, it may be a good idea.
Namespaces are one honking great idea -- let's do more of those!
"""

# ===================================== #

# How to pretty print dictionaries
import json
json.dumps(my_mapping, indent=4, sort_keys=True)
"""
{
  "a": 23,
  "b": 42,
  "c": 12648430
}
"""

# ===================================== #

# Function argument unpacking
def myfunc(x, y, z):
  print(x, y, z)

tuple_vec = (1, 0, 1)
dict_vec = {'x': 1, 'y': 0, 'z': 1}

myfunc(*tuple_vec)
# 1, 0, 1
myfunc(**dict_vec)
# 1, 0, 1

# ===================================== #

# How to time execution of code snippets
import timeit
timeit.timeit('"-".join(str(n) for n in range(100))', number=10000)
# 0.3412662749997253

timeit.timeit('"-".join([str(n) for n in range(100)])', number=10000)
# 0.2996307989997149

timeit.timeit('"-".join(map(str, range(100)))', number=10000)
# 0.24581470699922647

# ===================================== #

# Shorthand for swapping variables (without a temp)
a = 23
b = 42

# classic way:
tmp = a
a = b
b = tmp

# pythonic way:
a, b = b, a

# ===================================== #

# "is" vs "=="
# "is" expressions evaluate to True if two variables point to the same object
# "==" evaluates to True if the objects referred to by the variables are equal
a = [1, 2, 3]
b = a
c = list(a)

a == b
# True
a is b
# True

a == c
# True
a is c
# False

# ===================================== #

# Functions are first-class citizens
# They can be passed as arguments to other functions,
# returned as values from other functions, and
# assigned to variables and stored in data structures.

def myfunc(a, b):
  return a + b
funcs = [myfunc]
funcs[0]
# <function myfunc at 0x107012230>
funcs[0](2, 3)
# 5

# ===================================== #

# Use functions to emulate a switch block
def dispatch_if(operator, x, y):
  if operator == 'add':
    return x + y
  elif operator == 'sub':
    return x - y
  elif operator == 'mul':
    return x * y
  elif operator == 'div':
    return x / y
  else:
    return None

def dispatch_dict(operator, x, y):
  return {
    'add': lambda: x + y,
    'sub': lambda: x - y,
    'mul': lambda: x * y,
    'div': lambda: x / y,
  }.get(operator, lambda: None)()

dispatch_if('mul', 2, 8)
# 16
dispatch_dict('mul', 2, 8)
# 16
dispatch_if('unknown', 2, 8)
# None
dispatch_dict('unknown', 2, 8)
# None

# ===================================== #

# Run a simple HTTP server (3.x)
# (This will serve the current directory at http://localhost:8000)
$ python3 -m http.server

# ===================================== #

# List comprehensions are awesome
vals = [expression
        for value in collection
        if condition]

# is equivalent to:
vals = []
for value in collection:
  if condition:
    vals.append(expression)

# Example:
even_squares = [x * x for x in range(10) if not x % 2]
even_squares
# [0, 4, 16, 36, 64]

# ===================================== #

# Use type annotations for hints (3.5+)
def my_add(a: int, b: int) -> int:
  return a + b

# ===================================== #

# Using list slice syntax makes list manipulation easy
# You can clear all elements from a list:
lst = [1, 2, 3, 4, 5]
del lst[:]
print(lst)
# []

# You can replace all elements of a list without creating a new list object:
a = lst
lst[:] = [7, 8, 9]
print(lst)
# [7, 8, 9]
print(a)
# [7, 8, 9]
print(a is lst)
# True

# You can also create a (shallow) copy of a list:
b = lst[:]
print(b)
# [7, 8, 9]
print(b is lst)
# False

# ===================================== #

# Fun little Python easter egg (2.7+)
import antigravity

# ===================================== #

# Find most common elements in an iterable (list, dict, etc.)
import collections
c = collections.Counter('helloworld')
print(c)
# Counter({'l': 3, 'o': 2, 'e': 1, 'd': 1, 'h': 1, 'r': 1, 'w': 1})
print(c.most_common(3))
# [('l', 3), ('o', 2), ('e', 1)]

# ===================================== #

# Get all permutations from an iterable (list, dict, etc.)
import itertools
for p in itertools.permutations('ABCD'):
  print(p)
"""
('A', 'B', 'C', 'D')
('A', 'B', 'D', 'C')
('A', 'C', 'B', 'D')
('A', 'C', 'D', 'B')
('A', 'D', 'B', 'C')
('A', 'D', 'C', 'B')
('B', 'A', 'C', 'D')
('B', 'A', 'D', 'C')
('B', 'C', 'A', 'D')
('B', 'C', 'D', 'A')
('B', 'D', 'A', 'C')
('B', 'D', 'C', 'A')
('C', 'A', 'B', 'D')
('C', 'A', 'D', 'B')
('C', 'B', 'A', 'D')
('C', 'B', 'D', 'A')
('C', 'D', 'A', 'B')
('C', 'D', 'B', 'A')
('D', 'A', 'B', 'C')
('D', 'A', 'C', 'B')
('D', 'B', 'A', 'C')
('D', 'B', 'C', 'A')
('D', 'C', 'A', 'B')
('D', 'C', 'B', 'A')
"""

# ===================================== #

# __repr__ vs. __str__
# Emulate what the std lib does:
import datetime
today = datetime.date.today()

# Result of __str__ should be readable:
str(today)
# '2017-02-02'

# Result of __repr__ should be unambiguous:
repr(today)
# 'datetime.date(2017, 2, 2)'

# Python interpreter sessions use __repr__ to inspect objects:
>>> today
# datetime.date(2017, 2, 2)

# ===================================== #

# Disassemble functions into their Python VM bytcode
def greet(name):
  return 'Hello, ' + name + '!'
greet('Dan')
# 'Hello, Dan!'

import dis
dis.dis(greet)
"""
2   0 LOAD_CONST     1 ('Hello, ')
    2 LOAD_FAST      0 (name)
    4 BINARY_ADD
    6 LOAD_CONST     2 ('!')
    8 BINARY_ADD
   10 RETURN_VALUE
"""

# ===================================== #

# @classmethod vs @staticmethod vs "plain" methods
class MyClass:
  def method(self):
    """
    Instance methods need a class instance and
    can access the instance through `self`.
    """
    return 'instance method called', self

  @classmethod
  def classmethod(cls):
    """
    Class methods don't need a class instance.
    They can't access the instance (self) but
    they have access to the class itself via `cls`.
    """
    return 'class method called', cls

  @staticmethod
  def staticmethod():
    """
    Static methods don't have access to `cls` or `self`.
    They work like regular functions but belong to
    the class's namespace.
    """
    return 'static method called'

# All methods types can be called on a class instance:
obj = MyClass()
print(obj.method())
# ('instance method called', <MyClass instance at 0x1019381b8>)
print(obj.classmethod())
# ('class method called', <class MyClass at 0x101a2f4c8>)
print(obj.staticmethod())
# 'static method called'

# Calling instance methods fails if we only have the class object:
print(MyClass.classmethod())
# ('class method called', <class MyClass at 0x101a2f4c8>)
print(MyClass.staticmethod())
# 'static method called'
# print(MyClass.method())
"""
TypeError:
    "unbound method method() must be called with MyClass "
    "instance as first argument (got nothing instead)"
"""

# ===================================== #

# How to use lambda functions
add = lambda x, y: x + y
add(5, 3)
# 8

# You could declare the same add() function with the def keyword:
def add(x, y):
  return x + y
add(5, 3)
# 8

# So what's the big fuss about? Lambdas are *function expressions*:
(lambda x, y: x + y)(5, 3)
# 8

# Lambda functions are single-expression
# functions that are not necessarily bound
# to a name (they can be anonymous).

# Lambda functions can't use regular
# Python statements and always include an
# implicit `return` statement.

# ===================================== #

# Use IP addresses
import ipaddress
ipaddress.ip_address('192.168.1.2')
# IPv4Address('192.168.1.2')
ipaddress.ip_address('2001:af3::')
# IPv6Address('2001:af3::')

# ===================================== #

# Get the name of object, class, or function at runtime
class MyClass: pass
def myfunc(): pass

obj = MyClass()
obj.__class__.__name__
# 'MyClass'
myfunc.__name__
# 'myfunc'

# ===================================== #

# Check for class inheritance relationships
class BaseClass: pass
class SubClass(BaseClass): pass

issubclass(SubClass, BaseClass)
# True
issubclass(SubClass, object)
# True
issubclass(BaseClass, SubClass)
# False

# ===================================== #

# Use unicode characters in variable names
π = math.pi
class Spin̈alTap: pass
Spin̈alTap()
# <Spin̈alTap object at 0x10e58d908>

# Only letter-like characters work, however:
🍺 = "beer"
"""
SyntaxError: "invalid character in identifier"
"""

# ===================================== #

# Get global and local variables
# "globals()" returns a dict with all global variables in the current scope:
globals()
# {...}

# "locals()" does the same but for all local variables in the current scope:
locals()
# {...}

# ===================================== #

# Get traceback even when python fails (e.g. from a segmentation fault)
import faulthandler
faulthandler.enable()

# Can also be enabled with "python -X faulthandler" from the command line

# ===================================== #

# ===================================== #

# # Virtual Environments ("virtualenvs") keep
# your project dependencies separated.
# They help you avoid version conflicts
# between packages and different versions
# of the Python runtime.

# Before creating & activating a virtualenv:
# `python` and `pip` map to the system
# version of the Python interpreter
# (e.g. Python 2.7)
$ which python
/usr/local/bin/python

# Let's create a fresh virtualenv using
# another version of Python (Python 3):
$ python3 -m venv ./venv

# A virtualenv is just a "Python
# environment in a folder":
$ ls ./venv
bin      include    lib      pyvenv.cfg

# Activating a virtualenv configures the
# current shell session to use the python
# (and pip) commands from the virtualenv
# folder instead of the global environment:
$ source ./venv/bin/activate

# Note how activating a virtualenv modifies
# your shell prompt with a little note
# showing the name of the virtualenv folder:
(venv) $ echo "wee!"

# With an active virtualenv, the `python`
# command maps to the interpreter binary
# *inside the active virtualenv*:
(venv) $ which python
/Users/dan/my-project/venv/bin/python3

# Installing new libraries and frameworks
# with `pip` now installs them *into the
# virtualenv sandbox*, leaving your global
# environment (and any other virtualenvs)
# completely unmodified:
(venv) $ pip install requests

# To get back to the global Python
# environment, run the following command:
(venv) $ deactivate

# (See how the prompt changed back
# to "normal" again?)
$ echo "yay!"

# Deactivating the virtualenv flipped the
# `python` and `pip` commands back to
# the global environment:
$ which python
/usr/local/bin/python

# ===================================== #

# You can `else` statements with `for` and `while` blocks
def contains(haystack, needle):
  for item in haystack:
    if needle == haystack:
      break
  else:
    # The `else` here is a "completion clause" that runs only if the loop ran to completion
    # without hitting a `break` statement.
    raise ValueError('needle not found')

# ===================================== #

# Pythonic ways of checking if all items in a list are equal;
# Ordered from "most Pythonic" to "least Pythonic" and "least
# efficient" to "most efficient". The len(set()) solution is
# idiomatic, but constructing a set is less efficient memory
# and speed-wise.

lst = ['a', 'a', 'a']

len(set(lst)) == 1
# True

all(x == lst[0] for x in lst)
# True

lst.count(lst[0]) == len(lst)
# True

# ===================================== #

# In Python 3.4+ you can use
# contextlib.suppress() to selectively
# ignore specific exceptions:

import contextlib

with contextlib.suppress(FileNotFoundError):
  os.remove('somefile.tmp')

# This is equivalent to:

try:
  os.remove('somefile.tmp')
except FileNotFoundError:
  pass

# contextlib.suppress docstring:
#
# "Return a context manager that suppresses any
#  of the specified exceptions if they occur in the body
#  of a with statement and then resumes execution with
#  the first statement following the end of
#  the with statement."

# ===================================== #

# In Python 3 you can use a bare "*" asterisk
# in function parameter lists to force the
# caller to use keyword arguments for certain
# parameters:

def f(a, b, *, c='x', d='y', e='z'):
  return 'Hello'

# To pass the value for c, d, and e you
# will need to explicitly pass it as
# "key=value" named arguments:
f(1, 2, 'p', 'q', 'v')
# TypeError:
# "f() takes 2 positional arguments but 5 were given"

f(1, 2, c='p', d='q',e='v')
# 'Hello'

# ===================================== #

# Python 3.5+ allows passing multiple sets
# of keyword arguments ("kwargs") to a
# function within a single call, using
# the "**" syntax:

def process_data(a, b, c, d):
  print(a, b, c, d)

x = {'a': 1, 'b': 2}
y = {'c': 3, 'd': 4}

process_data(**x, **y)
# 1 2 3 4

process_data(**x, c=23, d=42)
# 1 2 23 42

# ===================================== #
```
