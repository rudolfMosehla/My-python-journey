# Python Essentials 1 — Module 3

**Cisco Networking Academy / OpenEDG Python Institute**
Learner: Team Forge · Skill Pods Program

This document covers all 7 sections of Module 3: conditional execution, loops, logic/bitwise operators, and Python lists (including copying, slicing, and comprehension).

---

## Table of Contents

1. [Comparison Operators & Conditional Statements](#1-comparison-operators--conditional-statements)
2. [Loops](#2-loops)
3. [Logic and Bitwise Operators](#3-logic-and-bitwise-operators)
4. [Lists](#4-lists)
5. [Sorting Lists](#5-sorting-lists)
6. [References, Slicing, and Membership](#6-references-slicing-and-membership)
7. [List Comprehension & Nested Lists](#7-list-comprehension--nested-lists)

---

## 1. Comparison Operators & Conditional Statements

### Comparison operators

Every comparison operator returns a Boolean (`True` or `False`).

| Operator | Meaning | Example (`x=5, y=5, z=3`) |
|---|---|---|
| `==` | equal to | `x == y` → `True` |
| `!=` | not equal to | `x != z` → `True` |
| `>` | greater than | `x > z` → `True` |
| `<` | less than | `z < x` → `True` |
| `>=` | greater than or equal to | `x >= y` → `True` |
| `<=` | less than or equal to | `x <= y` → `True` |

>  **Common bug:** `=` assigns a value, `==` compares two values. `if x = 5:` is a syntax error — you need `if x == 5:`.

### Conditional statements

```python
# single if
if x == 10:
    print("x is equal to 10")

# if-else
if x < 10:
    print("less than 10")
else:
    print("10 or more")

# if-elif-else
if x > 15:
    print("x > 15")
elif x > 10:
    print("x > 10")
elif x > 5:
    print("x > 5")
else:
    print("x <= 5")
```

**Key distinction:** with separate `if` statements, *every* condition is checked independently — more than one block can run. With `if-elif-else`, Python stops at the **first** `True` branch and skips the rest.

### Combining conditions

```python
if age >= 13 and age <= 19:
    print("Teenager")
```

`and` requires **both** sides to be `True`. `or` requires **at least one** side to be `True`.

### Nested conditionals

An `if` can live inside another `if`/`else` block:

```python
age = int(input("Enter your age: "))

if age < 13:
    print("Child")
elif age >= 13 and age <= 19:
    print("Teenager")
else:
    if age >= 65:
        print("Senior")
    else:
        print("Adult")
```

>  **`input()` always returns a string.** Comparing a string to an int (`"10" < 13`) raises `TypeError`. Convert with `int(input(...))` first.

---

## 2. Loops

### `while` loop

Repeats **while** a condition is `True`. The condition is checked **before** every run, including the first.

```python
counter = 5
while counter > 2:
    print(counter)
    counter -= 1
# Output: 5 4 3   (2 is never printed — the check fails before it prints)
```

### `for` loop

Iterates over a sequence (string, list, `range()`, etc.), running once per item.

```python
word = "Python"
for letter in word:
    print(letter, end="*")
# Output: P*y*t*h*o*n*
```

`end=` overrides `print()`'s default newline — useful for controlling layout.

### `range(start, stop, step)`

- `start` — optional, defaults to `0`
- `stop` — required, **never included** in the output
- `step` — optional, defaults to `1` (can be negative to count down)

```python
for i in range(3):
    print(i, end=" ")          # 0 1 2

for i in range(6, 1, -2):
    print(i, end=" ")          # 6 4 2
```

### `break` and `continue`

```python
# break — exits the loop entirely
for letter in "OpenEDG Python Institute":
    if letter == "P":
        break
    print(letter, end="")
# Output: OpenEDG 

# continue — skips just the current iteration
for letter in "pyxpyxpyx":
    if letter == "x":
        continue
    print(letter, end="")
# Output: pypypy
```

### The loop `else` clause

Runs **only if the loop finished normally** — i.e., was *not* stopped by `break`.

```python
n = 0
while n != 3:
    print(n)
    n += 1
else:
    print(n, "else")
# Output: 0 1 2 / 3 else

n = 0
while n != 5:
    print(n)
    n += 1
    if n == 3:
        break
else:
    print(n, "else")
# Output: 0 1 2   ("else" never runs — break interrupted the loop)
```

---

## 3. Logic and Bitwise Operators

### Logical operators

| Operator | Rule | Example |
|---|---|---|
| `and` | both sides must be `True` | `True and False` → `False` |
| `or` | at least one side must be `True` | `True or False` → `True` |
| `not` | flips the result | `not True` → `False` |

### Bitwise operators

Operate on the **binary representation** of numbers, bit by bit. Example values: `x = 15` (`0000 1111`), `y = 16` (`0001 0000`).

| Operator | Name | Rule (per bit pair) | Example |
|---|---|---|---|
| `&` | AND | `1` only if **both** bits are `1` | `x & y = 0` |
| `\|` | OR | `1` if **either** bit is `1` | `x \| y = 31` |
| `^` | XOR | `1` only if the bits are **different** | `x ^ y = 31` |
| `~` | NOT | flips every bit; shortcut: `~x = -(x + 1)` | `~x = -16` |
| `>>` | right shift | slides bits right (≈ divide by `2ⁿ`) | `y >> 1 = 8` |
| `<<` | left shift | slides bits left (≈ multiply by `2ⁿ`) | `y << 3 = 128` |

```python
print(12 & 10)   # 8
print(12 | 10)   # 14
print(12 ^ 10)   # 6
print(~12)       # -13
print(12 >> 2)   # 3
print(12 << 2)   # 48
```

---

## 4. Lists

A list is an **ordered, mutable** collection of items, written between square brackets.

```python
my_list = [1, None, True, "I am a string", 256, 0]
```

### Indexing

Indexes start at `0`. Negative indexes count from the end (`-1` is the last item).

```python
print(my_list[3])    # "I am a string"
print(my_list[-1])   # 0
```

### Changing, adding, and removing items

```python
my_list[1] = "?"              # replace an item
my_list.insert(0, "first")    # insert at a given position
my_list.append("last")        # add to the end
del my_list[2]                # delete one item by index
del my_list                   # delete the entire variable
```

### `len()` — a function, not a method

```python
print(len(my_list))
```

### Looping through a list

```python
for color in ["white", "purple", "blue"]:
    print(color)
```

### Nested lists

```python
my_list = [1, 'a', ["list", 64, [0, 1], False]]
print(len(my_list))     # 3 — the inner list counts as ONE item
```

### Function vs. method

| | Function | Method |
|---|---|---|
| Shape | `result = function(arg)` | `result = data.method(arg)` |
| Example | `len(my_list)` | `my_list.append(x)` |

---

## 5. Sorting Lists

```python
lst = [5, 3, 1, 2, 4]

lst.sort()
print(lst)        # [1, 2, 3, 4, 5]

lst.reverse()
print(lst)        # [5, 4, 3, 2, 1]
```

- `sort()` — orders the list from smallest to largest.
- `reverse()` — flips the current order; it does **not** sort.
- Combine `sort()` then `reverse()` for largest-to-smallest order.

>  **Trap:** `sort()` and `reverse()` change the list **in place** and return `None`. Never write `my_list = my_list.sort()` — this overwrites your list with `None`.

```python
names = ["Zara", "Adam", "Mia", "Ben"]
names = names.sort()
print(names)   # None   — the sorted list was thrown away

names = ["Zara", "Adam", "Mia", "Ben"]
names.sort()
print(names)   # ['Adam', 'Ben', 'Mia', 'Zara']  
```

---

## 6. References, Slicing, and Membership

### Assignment copies the reference, not the list

```python
vehicles_one = ['car', 'bicycle', 'motor']
vehicles_two = vehicles_one     # both names point to the SAME list
del vehicles_one[0]
print(vehicles_two)             # ['bicycle', 'motor'] — affected too!
```

### Slicing makes a genuine, independent copy

```python
colors = ['red', 'green', 'orange']
copy_whole = colors[:]          # copies the entire list
copy_part = colors[0:2]         # copies part of the list

del colors[0]
print(colors)       # ['green', 'orange']
print(copy_whole)   # ['red', 'green', 'orange'] — unaffected
```

### Slice syntax: `list[start:end]`

- `start` and `end` are both optional.
- `end` is never included (same "stop before" rule as `range()`).
- Negative indexes work in slices too.

```python
sample_list = ["A", "B", "C", "D", "E"]
print(sample_list[2:-1])   # ['C', 'D']

my_list = [1, 2, 3, 4, 5]
print(my_list[2:])    # [3, 4, 5]
print(my_list[:2])    # [1, 2]
print(my_list[-2:])   # [4, 5]
```

### Deleting slices

```python
my_list = [1, 2, 3, 4, 5]
del my_list[0:2]
print(my_list)     # [3, 4, 5]

del my_list[:]
print(my_list)     # [] — empties the list, keeps the variable alive
```

### Membership: `in` / `not in`

```python
my_list = ["A", "B", 1, 2]
print("A" in my_list)        # True
print("C" not in my_list)    # True
print(2 not in my_list)      # False — 2 IS in the list
```

---

## 7. List Comprehension & Nested Lists

### List comprehension

A concise way to build a list from a loop, in one line.

```
[expression for element in list if conditional]
```

Equivalent to:

```python
for element in list:
    if conditional:
        expression
```

```python
cubed = [num ** 3 for num in range(5)]
print(cubed)   # [0, 1, 8, 27, 64]

evens = [num for num in range(10) if num % 2 == 0]
print(evens)   # [0, 2, 4, 6, 8]
```

### Nested lists (matrices)

A list of lists can represent a 2D grid — index twice: `[row][column]`.

```python
table = [[":(", ":)", ":(", ":)"],
         [":)", ":(", ":)", ":)"],
         [":(", ":)", ":)", ":("],
         [":)", ":)", ":)", ":("]]

print(table[0][0])   # ':('
print(table[0][3])   # ':)'
```

### N-dimensional nesting

Lists can nest as deeply as needed. A 3D structure (a "cube") needs **three** indexes to reach a single item: `[block][row][item]`.

```python
cube = [[[':(', 'x', 'x'], [':)', 'x', 'x'], [':(', 'x', 'x']],
        [[':)', 'x', 'x'], [':(', 'x', 'x'], [':)', 'x', 'x']],
        [[':(', 'x', 'x'], [':)', 'x', 'x'], [':)', 'x', 'x']]]

print(cube[0][0][0])   # ':('
print(cube[2][2][0])   # ':)'
```

---

## Summary

| Section | Topic |
|---|---|
| 1 | Comparison operators, `if` / `elif` / `else`, nesting |
| 2 | `while`, `for`, `range()`, `break`, `continue`, loop `else` |
| 3 | `and` / `or` / `not`, bitwise operators, binary |
| 4 | List basics — indexing, adding, removing, looping |
| 5 | `sort()` and `reverse()` |
| 6 | References vs. copies, slicing, `in` / `not in` |
| 7 | List comprehension, nested (multi-dimensional) lists |

*Compiled as part of the Skill Pods program, Team Forge.*
