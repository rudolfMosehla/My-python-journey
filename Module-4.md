# Python Essentials 1 — Module 4

**Cisco Networking Academy / OpenEDG Python Institute**
Learner: Team Forge · Skill Pods Program

This document covers all 7 sections of Module 4: functions, parameters, return values, variable scope, recursion, tuples and dictionaries, and errors and exceptions.

---

## Table of Contents

1. [Functions](#1-functions)
2. [Function Parameters and Argument Passing](#2-function-parameters-and-argument-passing)
3. [Returning Values](#3-returning-values)
4. [Variable Scope](#4-variable-scope)
5. [Recursion](#5-recursion)
6. [Tuples and Dictionaries](#6-tuples-and-dictionaries)
7. [Errors and Exceptions](#7-errors-and-exceptions)

---

## 1. Functions

A **function** is a named block of code that performs one specific task when it is called. Functions make code reusable, better organised, and easier to read. They can take **parameters** (inputs) and give back **return values** (outputs).

### Four types of function

| Type | Description |
|---|---|
| Built-in | Part of Python itself, e.g. `print()`, `len()`, `input()` |
| From modules | Come from pre-installed modules (covered in Python Essentials 2) |
| User-defined | Written by you with `def` |
| Lambda | A short-form function (covered in Python Essentials 2) |

### Defining and calling

```python
def message():          # defining the function
    print("Hello")      # body of the function

message()               # calling the function
```

>  **Defining is not calling.** `def` only teaches Python what the function does. Nothing runs until you call it with `message()`. Forgetting the call produces no error and no output.

### A function with one parameter

```python
def hello(name):
    print("Hello,", name)

name = input("Enter your name: ")
hello(name)
```

The parameter name inside `def` does not have to match the variable you pass in. Python matches values to parameters by **position**, not by name.

---

## 2. Function Parameters and Argument Passing

A function can have as many parameters as you need.

```python
def hi_all(name_1, name_2):
    print("Hi,", name_2)
    print("Hi,", name_1)

hi_all("Sebastian", "Konrad")
# Hi, Konrad
# Hi, Sebastian
```

The body does not have to use parameters in the order they were defined.

### Positional arguments — order matters

```python
def subtra(a, b):
    print(a - b)

subtra(5, 2)    # 3
subtra(2, 5)    # -3
```

### Keyword (named) arguments — order does not matter

```python
subtra(a=5, b=2)    # 3
subtra(b=2, a=5)    # 3
```

### Mixing the two

```python
subtra(5, b=2)      # 3
subtra(5, 2)        # 3
```

 **Positional arguments must come before keyword arguments.** Once you use a keyword argument, every argument after it must also be a keyword argument.
>
> ```python
> subtra(a=5, 2)    # SyntaxError
> ```

### Default parameter values

```python
def name(first_name, last_name="Smith"):
    print(first_name, last_name)

name("Andy")                # Andy Smith
name("Betty", "Johnson")    # Betty Johnson (default replaced)
```

If the caller leaves the argument out, the default is used. If the caller supplies one, it overrides the default.

---

## 3. Returning Values

`return` hands a value back to whoever called the function, and **exits the function immediately**.

```python
def multiply(a, b):
    return a * b

print(multiply(3, 4))    # 12
```

A bare `return` with no value gives back `None`:

```python
def multiply(a, b):
    return

print(multiply(3, 4))    # None
```

### Storing the result

```python
def wishes():
    return "Happy Birthday!"

w = wishes()
print(w)    # Happy Birthday!
```

### `print()` inside a function vs `return`

These are two separate actions.

```python
def wishes():
    print("My Wishes")
    return "Happy Birthday"

wishes()
# My Wishes

print(wishes())
# My Wishes
# Happy Birthday
```

- A `print()` inside the function runs every time the function is called.
- A returned value is only **seen** if something outside uses it (prints it, stores it, and so on).

### Lists and functions

A list can be passed in as an argument:

```python
def hi_everybody(my_list):
    for name in my_list:
        print("Hi,", name)

hi_everybody(["Adam", "John", "Lucy"])
```

A list can also be the result:

```python
def create_list(n):
    my_list = []
    for i in range(n):
        my_list.append(i)
    return my_list

print(create_list(5))    # [0, 1, 2, 3, 4]
```

---

## 4. Variable Scope

**Scope** is the part of a program where a variable can be seen.

### Outer variables are visible inside a function

```python
var = 2

def mult_by_var(x):
    return x * var

print(mult_by_var(7))    # 14
```

### A variable created inside a function shadows an outer one of the same name

```python
def mult(x):
    var = 5
    return x * var

print(mult(7))    # 35
```

```python
def mult(x):
    var = 7
    return x * var

var = 3
print(mult(7))    # 49 — the inner var (7) wins, the outer var (3) is ignored
```

### Variables created inside a function do not exist outside it

```python
def adding(x):
    var = 7
    return x + var

print(adding(4))    # 11
print(var)          # NameError: name 'var' is not defined
```

### The `global` keyword

`global` tells Python to use the real outer variable instead of creating a new local one.

```python
var = 2
print(var)          # 2

def return_var():
    global var
    var = 5
    return var

print(return_var()) # 5
print(var)          # 5 — the outer variable was permanently changed
```

 Use `global` carefully. It lets a function change something outside itself, so its effects are no longer contained in its own return value.

---

## 5. Recursion

**Recursion** is when a function calls **itself**. A recursive function needs a **base case**, a condition that stops it from calling itself again.

```python
def factorial(n):
    if n == 1:                  # base case (termination condition)
        return 1
    else:
        return n * factorial(n - 1)

print(factorial(4))    # 24  (4 * 3 * 2 * 1)
```

### Advantages and disadvantages

| Advantages | Disadvantages |
|---|---|
| Can give clean, elegant code | Easy to write one that never terminates |
| Divides a problem into smaller pieces | Recursive calls use a lot of memory |
| | Can be inefficient |

 **Without a base case**, a recursive function never stops calling itself.

---

## 6. Tuples and Dictionaries

### Sequence types and mutability

- A **sequence type** stores multiple values that can be read one after another. A sequence is data that a `for` loop can scan.
- **Mutable** data can be changed in place (lists, dictionaries). **Immutable** data cannot (tuples).

### Tuples

A tuple is an **ordered, immutable** collection, written in round brackets.

```python
my_tuple = (1, 2.0, "string", [3, 4], (5, ), True)
print(my_tuple[3])    # [3, 4]
```

Items can be of different types, and tuples can contain lists or other tuples.

#### Creating tuples

```python
empty_tuple = ()
one_elem_tuple_1 = ("one", )     # brackets and a comma
one_elem_tuple_2 = "one",        # just a comma
```

>  **The comma makes the tuple.** Without it you get an ordinary value:
>
> ```python
> my_tuple_1 = 1,
> my_tuple_2 = 1
> print(type(my_tuple_1))    # <class 'tuple'>
> print(type(my_tuple_2))    # <class 'int'>
> ```

#### Tuples cannot be changed

```python
my_tuple = (1, 2.0, "string", [3, 4], (5, ), True)
my_tuple[2] = "guitar"
# TypeError: 'tuple' object does not support item assignment
```

You cannot append to, modify, or remove tuple elements. You **can** delete the whole tuple:

```python
my_tuple = 1, 2, 3,
del my_tuple
print(my_tuple)    # NameError: name 'my_tuple' is not defined
```

#### What tuples can do

```python
tuple_1 = (1, 2, 3)
tuple_2 = (1, 2, 3, 4)

for elem in tuple_1:         # loop through
    print(elem)

print(5 in tuple_2)          # False
print(5 not in tuple_2)      # True
print(len(tuple_2))          # 4
print(tuple_1 + tuple_2)     # (1, 2, 3, 1, 2, 3, 4)   — a new tuple
print(tuple_1 * 2)           # (1, 2, 3, 1, 2, 3)       — a new tuple
```

`+` and `*` build **new** tuples. They do not change the originals.

#### Converting with `tuple()` and `list()`

```python
my_list = [2, 4, 6]
tup = tuple(my_list)         # (2, 4, 6)
back = list(tup)             # [2, 4, 6]
```

### Dictionaries

A dictionary is a **mutable** collection of **key: value** pairs, written in curly braces. You look values up by key, not by position.

```python
dictionary = {"cat": "chat", "dog": "chien", "horse": "cheval"}
empty_dictionary = {}

print(dictionary["cat"])    # chat
```

Rules:

- Each key must be **unique**.
- A key must be an **immutable** type (number, string, tuple), never a list.
- Keys are **case-sensitive**: `'Suzy'` is not `'suzy'`.
- `len()` returns the number of key-value pairs.
- A dictionary is one-way: you look up values by key, not keys by value.
- Since Python 3.6, dictionaries keep the order pairs were added. Older versions did not.

#### Missing keys

```python
dictionary["lion"]    # KeyError: 'lion'
```

Check first with `in` (which tests **keys**):

```python
words = ["cat", "lion", "horse"]

for word in words:
    if word in dictionary:
        print(word, "->", dictionary[word])
    else:
        print(word, "is not in dictionary")
# cat -> chat
# lion is not in dictionary
# horse -> cheval
```

#### Changing, adding and removing

```python
dictionary["cat"] = "minou"      # existing key: value replaced
dictionary["swan"] = "cygne"     # new key: pair added
dictionary.update({"duck": "canard"})   # another way to add

del dictionary["dog"]            # remove a pair (error if the key is missing)
dictionary.popitem()             # remove the last item
```

> Assigning to a new key **creates** it in a dictionary. With a list, assigning to a non-existent index is an error.

#### Looping through a dictionary

```python
# keys()
for key in dictionary.keys():
    print(key, "->", dictionary[key])

# items() — each pair arrives as a (key, value) tuple
for english, french in dictionary.items():
    print(english, "->", french)

# values()
for french in dictionary.values():
    print(french)

# sorted keys
for key in sorted(dictionary.keys()):
    print(key)
```

### Tuples and dictionaries working together

A tuple can be a dictionary value. This program stores each student's scores in a tuple and averages them:

```python
school_class = {}

while True:
    name = input("Enter the student's name: ")
    if name == '':
        break

    score = int(input("Enter the student's score (0-10): "))
    if score not in range(0, 11):
        break

    if name in school_class:
        school_class[name] += (score,)
    else:
        school_class[name] = (score,)

for name in sorted(school_class.keys()):
    adding = 0
    counter = 0
    for score in school_class[name]:
        adding += score
        counter += 1
    print(name, ":", adding / counter)
```

---

## 7. Errors and Exceptions

Python has two kinds of error.

| | Syntax error | Exception |
|---|---|---|
| When it happens | Before anything runs (the parser cannot read the line) | While the code is running |
| Example | `print("Hello, World!)` | `print(1/0)` |
| Name shown | `SyntaxError` | `ZeroDivisionError`, `NameError`, `TypeError`, ... |

```python
print("Hello, World!)
#                    ^
# SyntaxError: EOL while scanning string literal
```

```python
print(1/0)
# Traceback (most recent call last):
#   File "main.py", line 1, in <module>
# ZeroDivisionError: division by zero
```

The **last line** of an error message names the exception and tells you what went wrong.

### Catching exceptions with `try` / `except`

```python
try:
    print(1/0)
except:
    print("Something went wrong, but the program keeps going.")

print("This line still runs.")
```

1. Python runs the `try` block.
2. If an exception occurs, the rest of the `try` block is skipped.
3. Python jumps to the `except` block and runs it.
4. The program continues after the whole `try`/`except`.

A common pattern is to keep asking until the input is valid:

```python
while True:
    try:
        number = int(input("Enter an integer number: "))
        print(number / 2)
        break
    except:
        print("Warning: the value entered is not a valid number. Try again...")
```

### Handling several exceptions

```python
while True:
    try:
        number = int(input("Enter an int number: "))
        print(5 / number)
        break
    except ValueError:
        print("Wrong value.")
    except ZeroDivisionError:
        print("Sorry. I cannot divide by zero.")
    except:
        print("I don't know what to do...")
```

- Use several `except` blocks, each naming a specific exception.
- If one `except` runs, the others are skipped.
- Name each built-in exception only **once**.
- Put the generic `except:` (no name) **last**: specific first, general last.

Several exceptions can share one `except`:

```python
except (ValueError, ZeroDivisionError):
    print("Wrong value or No division by zero rule broken.")
```

### Useful built-in exceptions

| Exception | Typical cause |
|---|---|
| `ZeroDivisionError` | Dividing by zero |
| `ValueError` | Right type, unusable value, e.g. `int("hello")` |
| `TypeError` | Wrong type for an operation, e.g. `"10" < 13` |
| `AttributeError` | Using a method that doesn't exist, e.g. `my_tuple.append(1)` |
| `SyntaxError` | The code can't be parsed |
| `NameError` | Using a name that doesn't exist |
| `KeyError` | Looking up a dictionary key that doesn't exist |
| `KeyboardInterrupt` | The user presses Ctrl-C or Delete |

### Testing and debugging tips

- Use **print debugging** to see what values your code is working with.
- Ask someone else to read your code.
- Isolate the fragment of code that is causing trouble.
- Test functions with predictable argument values.
- Plan for wrong input from users.
- Comment out the parts of code that obscure the problem.
- Take breaks and return with fresh eyes.

---

## Summary

| Section | Topic |
|---|---|
| 1 | What functions are, `def`, defining vs calling, one parameter |
| 2 | Multiple parameters, positional / keyword / mixed arguments, default values |
| 3 | `return`, `None`, `print` vs `return`, lists in and out of functions |
| 4 | Scope: outer variables, shadowing, private inner variables, `global` |
| 5 | Recursion, base case, factorial |
| 6 | Tuples (immutable) and dictionaries (key-value), `keys()` / `values()` / `items()` |
| 7 | Syntax errors vs exceptions, `try` / `except`, multiple exceptions, debugging |

*Compiled as part of the Skill Pods program, Team Forge.*
