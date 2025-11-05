© 2025 Geethanjali Group of Institutions. All Rights Reserved. Unauthorized use or distribution is prohibited.

# Python Study Guide

---

## 1. Python Syntax & Basics

### 🔹 Python Characteristics
- Interpreted, dynamically typed, high-level, multi-paradigm (supports OOP, functional, procedural).
- Indentation-based block structure (no braces `{}` like Java/C++).
- No need to declare variable types; type inferred at runtime.

```python
x = 10        # int
y = 3.14      # float
name = "Harish"  # string
```

### 🔹 Comments
```python
# Single-line comment
"""
Multi-line comment / docstring
"""
```

### 🔹 Input / Output
```python
name = input("Enter name: ")
print(f"Hello {name}")  # f-string formatting
```

### 🔹 Type Casting
```python
int("10")      # 10
str(123)        # "123"
float("3.14")  # 3.14
```

---

## 2. Data Types & Data Structures

| Type | Example | Notes |
|-------|---------|-------|
| `int` | `a = 10` | unlimited precision |
| `float` | `b = 3.14` | decimal numbers |
| `str` | `"hello"` | immutable |
| `bool` | `True/False` | logical ops |
| `list` | `[1,2,3]` | mutable, ordered |
| `tuple` | `(1,2,3)` | immutable, ordered |
| `set` | `{1,2,3}` | unordered, unique items |
| `dict` | `{"a":1, "b":2}` | key-value store |

### 🔹 List Operations
```python
nums = [1, 2, 3]
nums.append(4)
nums.insert(1, 10)
nums.remove(3)
nums.sort()
nums.reverse()
```

### 🔹 Dictionary
```python
student = {"name": "Harish", "cgpa": 8.7}
student["branch"] = "CSE"
for k, v in student.items():
    print(k, v)
```

### 🔹 Set
```python
s = {1, 2, 3}
s.add(4)
s.remove(2)
```

### Common Built-in Functions
`len(), type(), sorted(), range(), enumerate(), zip()`

---

## 3. Functions in Python

### 🔹 Defining Functions
```python
def add(a, b=0):   # default argument
    return a + b
```

### 🔹 `*args` and `**kwargs`
```python
def demo(*args, **kwargs):
    print(args, kwargs)
demo(1,2,3, name="Harish")
```

### 🔹 Lambda Function
```python
square = lambda x: x*x
print(square(5))  # 25
```

### 🔹 Map, Filter, Reduce
```python
from functools import reduce
nums = [1,2,3,4]
print(list(map(lambda x: x*x, nums)))  # [1,4,9,16]
print(list(filter(lambda x: x%2==0, nums)))  # [2,4]
print(reduce(lambda a,b: a+b, nums))  # 10
```

---

## 4. OOP in Python

### 🔹 Class & Object
```python
class Student:
    college = "ABC"  # class variable
    def __init__(self, name, roll):  # constructor
        self.name = name
        self.roll = roll
    def display(self):
        print(self.name, self.roll)
```
st1 = Student("Harish", 101)
st1.display()
```

### 🔹 Inheritance
```python
class A:
    def show(self): print("A")
class B(A):      # Single Inheritance
    pass
```

### 🔹 Encapsulation, Polymorphism, Abstraction
- Private members use `__var`
- Method overriding supported

```python
class Base:
    def greet(self): print("Hello")
class Child(Base):
    def greet(self): print("Hi")  # overriding
```

---

## 5. File Handling

### 🔹 Modes: `r, w, a, r+, w+`
```python
with open("data.txt", "w") as f:
    f.write("Hello world")
```

### 🔹 Reading
```python
with open("data.txt", "r") as f:
    print(f.read())
```

> `with` auto-closes the file (context manager)

---

## 6. Exception Handling

```python
try:
    x = 10 / 0
except ZeroDivisionError:
    print("Cannot divide by zero")
except Exception as e:
    print("Error:", e)
finally:
    print("Cleanup code")
```

### 🔹 Raise custom exception
```python
if age < 18:
    raise ValueError("Not eligible")
```

---

## 7. Modules & Libraries

### 🔹 Importing
```python
import math
from datetime import datetime
```

### 🔹 Common Standard Libraries
| Library | Usage |
|---------|-------|
| `math` | math functions (`sqrt`, `pi`, etc.) |
| `datetime` | working with date/time |
| `os` | file system ops |
| `random` | random numbers |
| `sys` | interpreter info |

### 🔹 Creating Custom Module
```python
# file: utils.py
def greet(): print("Hello")

# main.py
import utils
utils.greet()
```

---

## 8. Important Python Gotchas (Asked in Interviews)

| Gotcha | Explanation |
|--------|-------------|
| `list1 = list2` | Both refer to same list (shallow copy) |
| `is` vs `==` | `is` → object identity, `==` → value comparison |
| Default args evaluated once | e.g. `def f(x, lst=[])` retains previous state |
| `int("010")` invalid in Python 3 | No octal literal without `0o` prefix |
| Mutable vs Immutable | list/set/dict mutable · str/int/tuple immutable |

```python
# Mutable default arg issue
def add_item(item, lst=[]):
    lst.append(item)
    return lst
print(add_item(1))  # [1]
print(add_item(2))  # [1, 2] ← bug!
```
**Fix:** use `None` as placeholder
```python
def add_item(item, lst=None):
    if lst is None: lst = []
    lst.append(item)
    return lst
```

---

## 9. Practice Questions
1. Write a function to count frequency of words in a file.
2. Implement a class `BankAccount` with deposit and withdraw methods.
3. Write a program to reverse a string without built-in methods.
4. Use lambda + filter to extract even numbers from list.
5. Explain difference between `tuple` and `list` with example.

---

## 10. Fast Revision Checklist
- [ ] Understand list vs tuple vs set vs dict differences
- [ ] Know how to write class, constructor, static/class methods
- [ ] Practice exception handling & file I/O
- [ ] Know how `*args` and `**kwargs` work
- [ ] Know basic library functions (`math`, `datetime`, `random`)
- [ ] Be able to write small programs in < 5 mins
