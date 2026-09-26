# 🐍 My Python Journey: Module 2 Recap

## Data Types, Variables, Basic Input/Output, and Operators

**Team:** Forge 
**Course:** Cisco Networking Academy, Python Essentials 1 (Module 2)

This is my documentation for Module 2, built up section by section as I learned. It covers all six sections: **functions and the print() function**, **literals**, **operators and expressions**, **variables**, **comments**, and **the input() function**.

---

##  Table of Contents

- [Section 1: The print() function](#section-1-the-print-function)
  - [What is a function?](#what-is-a-function)
  - [Built-in vs. user-defined functions](#built-in-vs-user-defined-functions)
  - [Calling a function](#calling-a-function)
  - [Python strings](#python-strings)
  - [What is an instruction?](#what-is-an-instruction)
  - [The backslash and escape characters](#the-backslash-and-escape-characters)
  - [Positional arguments](#positional-arguments)
  - [Keyword arguments](#keyword-arguments)
  - [Formatting output with sep and end](#formatting-output-with-sep-and-end)
  - [Section 1 summary](#section-1-summary)
- [Section 2: Literals](#section-2-literals)
  - [What is a literal?](#what-is-a-literal)
  - [Number systems: binary, octal, and hexadecimal](#number-systems-binary-octal-and-hexadecimal)
  - [Integers](#integers)
  - [Floating-point numbers](#floating-point-numbers)
  - [Apostrophes and quotes inside strings](#apostrophes-and-quotes-inside-strings)
  - [Boolean values](#boolean-values)
  - [Extra: the None literal](#extra-the-none-literal)
  - [Section 2 summary](#section-2-summary)
- [Section 3: Operators and expressions](#section-3-operators-and-expressions)
  - [What is an expression?](#what-is-an-expression)
  - [What is an operator?](#what-is-an-operator)
  - [Arithmetic operators](#arithmetic-operators)
  - [Unary and binary operators](#unary-and-binary-operators)
  - [Order of priority](#order-of-priority)
  - [Parentheses come first](#parentheses-come-first)
  - [Exponentiation binds right to left](#exponentiation-binds-right-to-left)
  - [Section 3 summary](#section-3-summary)
- [Section 4: Variables](#section-4-variables)
  - [What is a variable?](#what-is-a-variable)
  - [Naming a variable](#naming-a-variable)
  - [Python doesn't need declarations](#python-doesnt-need-declarations)
  - [The assignment operator](#the-assignment-operator)
  - [Compound assignment operators](#compound-assignment-operators)
  - [Changing a variable's value](#changing-a-variables-value)
  - [Combining text and variables](#combining-text-and-variables)
  - [Section 4 summary](#section-4-summary)
- [Section 5: Comments](#section-5-comments)
  - [What is a comment?](#what-is-a-comment)
  - [Multi-line comments and commenting out code](#multi-line-comments-and-commenting-out-code)
  - [Use meaningful variable names](#use-meaningful-variable-names)
  - [Keep comments accurate](#keep-comments-accurate)
  - [Why comments matter](#why-comments-matter)
  - [Section 5 summary](#section-5-summary)
- [Section 6: The input() function](#section-6-the-input-function)
  - [print() vs. input()](#print-vs-input)
  - [The prompt string](#the-prompt-string)
  - [The program waits for the user](#the-program-waits-for-the-user)
  - [Using input() to end a program](#using-input-to-end-a-program)
  - [input() always returns a string](#input-always-returns-a-string)
  - [Replicating strings](#replicating-strings)
  - [Section 6 summary](#section-6-summary)

---

## Section 1: The print() Function

### What is a function?

A **function** is a named, reusable piece of code that performs a task. Instead of writing the same instructions over and over, I can just **call** the function by name whenever I need it.

The very first function I used was `print()`, a **built-in function** that prints or outputs a specified message to the screen (the console window).

---

### Built-in vs. user-defined functions

Python functions come in two kinds:

- **Built-in functions**, like `print()`, are always available. I don't need to import anything to use them.
- **User-defined functions** are ones that a programmer (eventually, me) writes. I'll learn how to create my own later in the course.

Python 3.8 ships with **69 built-in functions**, listed alphabetically in the [Python Standard Library](https://docs.python.org/3/library/functions.html). `print()` is just one of many.

---

### Calling a function

Using a function is called **invoking** it, or a **function call**. To call a function, I write its **name**, followed by **parentheses**:

```python
print()
```

If I want to pass information into the function, I place **arguments** inside the parentheses, separated by **commas**:

```python
print("Hello,", "world!")
```

**Output:**

```
Hello, world!
```

An "empty" `print()`, with nothing inside the parentheses, simply outputs a **blank line**.

---

### Python strings

A **string** is text, and in Python it's marked out with quotes. I can use either:

```python
"I am a string"      # double quotes
'I am a string, too' # single quotes
```

Both work the same way. Which one I use is mostly a matter of style, or which is more convenient for the text I'm writing (as I saw in Section 2, with apostrophes and quotes).

---

### What is an instruction?

A computer program is a **collection of instructions**. An **instruction** is a single command that performs a specific task when it's executed, for example, printing a message to the screen.

This ties back to Module 1: a program is just a sequence of simple steps, and `print()` is one of the simplest instructions I can give.

---

### The backslash and escape characters

Inside a string, the **backslash (`\`)** is a special character. It tells Python that the **next character means something different** from normal. This is called an **escape character**.

The most common one is `\n`, the **newline character**, which starts a new output line:

```python
print("Hello,\nworld!")
```

**Output:**

```
Hello,
world!
```

---

### Positional arguments

A **positional argument** is one whose meaning comes from its **position** in the list of arguments. The first argument is output first, the second comes after it, and so on:

```python
print("one", "two", "three")
```

**Output:**

```
one two three
```

---

### Keyword arguments

A **keyword argument** is one whose meaning doesn't come from its position, but from a **keyword** (a special word) that identifies it. `sep` and `end`, covered next, are examples of keyword arguments.

---

### Formatting output with sep and end

`print()` has two useful keyword parameters for controlling how output looks:

- **`sep`** sets the **separator** placed between the arguments (the default is a single space)
- **`end`** sets what's printed **at the end** of the output (the default is a newline)

```python
print("H", "E", "L", "L", "O", sep="-")
```

**Output:**

```
H-E-L-L-O
```

```python
print("Loading", end="...")
print("done!")
```

**Output:**

```
Loading...done!
```

Because I set `end="..."` instead of the default newline, the second `print()` continued on the **same line**.

---

### Section 1 summary

1. The `print()` function is a **built-in function**. It prints or outputs a specified message to the screen (console window).
2. **Built-in functions** are always available and don't need to be imported, unlike **user-defined functions**. Python 3.8 has **69 built-in functions**, listed in the Python Standard Library.
3. To **call** a function (function invocation), I use its name followed by parentheses, and pass **arguments** inside the parentheses, separated by commas, e.g., `print("Hello,", "world!")`. An empty `print()` outputs a blank line.
4. Python **strings** are delimited with quotes, either double (`"..."`) or single (`'...'`).
5. Computer programs are collections of **instructions**: commands that perform a specific task when executed.
6. The **backslash (`\`)** is a special escape character in strings, for example `\n` starts a new output line.
7. **Positional arguments** get their meaning from their position: the second is output after the first, the third after the second, and so on.
8. **Keyword arguments** get their meaning from a keyword, not their position.
9. The `sep` and `end` parameters format `print()`'s output. `sep` sets the separator between arguments, e.g., `print("H", "E", "L", "L", "O", sep="-")`, and `end` sets what's printed at the end of the output.

---

## Section 2: Literals

### What is a literal?

A **literal** is a fixed value written directly into the code. It's the plainest way to represent data: I type the value exactly as it is, and Python understands it immediately.

Python has different kinds of literals. Two examples are:

- **Numeric literals**, like `123`
- **String literals**, like `"I am a literal."`

---

### Number systems: binary, octal, and hexadecimal

I normally count using the **decimal** system, which has 10 digits (0 to 9). Computers, though, are built around other number systems too:

- The **binary** system uses base 2, so it's made up of only `0`s and `1`s. For example, `1010` in binary is `10` in decimal.
- The **octal** system uses base 8.
- The **hexadecimal** system uses base 16. Since there are only 10 decimal digits, hexadecimal borrows six letters (`A` to `F`) to represent the extra values.

This connects back to Module 1: computers work with very simple values at their core, and binary is the most basic form of that.

---

### Integers

An **integer** (or **int**) is a whole number, written with **no fractional part**. It can be positive or negative:

```python
256
-1
```

---

### Floating-point numbers

A **floating-point number** (or **float**) is a number that **contains, or can contain, a fractional part**:

```python
1.27
```

Even a number like `2.0` counts as a float, because of the decimal point, even though the fractional part is zero.

---

### Apostrophes and quotes inside strings

Sometimes a string needs to contain a quote mark itself, and there are two ways to handle that:

**1. Use the escape character (`\`)** to tell Python the quote mark is part of the text, not the end of the string:

```python
'I\'m happy.'
```

**2. Use the opposite type of quote mark** to open and close the string:

```python
"I'm happy."                          # apostrophe inside double quotes
'He said "Python", not "typhoon"'     # double quotes inside single quotes
```

Both approaches work. I think the second one is usually easier to read.

---

### Boolean values

A **Boolean** value represents truth, and there are only two of them: **`True`** and **`False`**.

In a numeric context, Python treats:

- `1` as `True`
- `0` as `False`

---

### Extra: the None literal

Python has one more special literal: **`None`**. It's an object of type `NoneType`, and it's used to represent the **absence of a value**, rather than a zero, an empty string, or `False`. I'll learn more about how it's used later in the course.

---

### Section 2 summary

1. A **literal** is a notation for a fixed value written in code. Python has different kinds, such as **numeric literals** (e.g., `123`) and **string literals** (e.g., `"I am a literal."`).
2. The **binary** system uses base 2 (only `0`s and `1`s), for example `1010` in binary is `10` in decimal. The **octal** and **hexadecimal** systems use base 8 and base 16, and hexadecimal adds six letters to the decimal digits.
3. **Integers** are whole numbers with no fractional part, e.g., `256` or `-1`.
4. **Floats** are numbers with (or able to have) a fractional part, e.g., `1.27`.
5. To include an apostrophe or a quote inside a string, I can either use the **escape character** (e.g., `'I\'m happy.'`) or use the **opposite quote marks** (e.g., `"I'm happy."` or `'He said "Python"'`).
6. **Boolean values** are `True` and `False`. In a numeric context, `1` means `True` and `0` means `False`.
7. **Extra:** `None` is a special literal used to represent the **absence of a value**.

---

## Section 3: Operators and Expressions

### What is an expression?

An **expression** is a combination of values, variables, and operators (and later, function calls too) that Python can work out to give a single value.

The simplest expression is something like:

```python
1 + 2
```

Python evaluates this to `3`.

---

### What is an operator?

An **operator** is a special symbol or keyword that acts on values to perform an operation, usually a mathematical one. For example, the `*` operator multiplies two values:

```python
x * y
```

---

### Arithmetic operators

Python has these arithmetic operators:

| Operator | Name | Example | Result |
|---|---|---|---|
| `+` | Addition | `3 + 2` | `5` |
| `-` | Subtraction | `3 - 2` | `1` |
| `*` | Multiplication | `3 * 2` | `6` |
| `/` | Classic division | `5 / 2` | `2.5` |
| `%` | Modulus (remainder) | `5 % 2` | `1` |
| `**` | Exponentiation | `2 ** 3` | `8` |
| `//` | Floor (integer) division | `3 // 2.0` | `1.0` |

A few notes that stood out to me:

- `/` (classic division) **always returns a float**, even if the numbers divide evenly.
- `%` gives me the **remainder** left over after dividing, for example `5 % 2 = 1` because 5 ÷ 2 leaves a remainder of 1.
- `**` means "raised to the power of," so `2 ** 3` is `2 * 2 * 2`, which is `8`.
- `//` divides and then **rounds down** to the nearest whole number, so `3 // 2.0 = 1.0`.

---

### Unary and binary operators

- A **unary operator** works on **one operand**, for example `-1` or `+3`.
- A **binary operator** works on **two operands**, for example `4 + 5` or `12 % 5`.

The same symbol, like `-`, can act as either one depending on how many values are next to it.

---

### Order of priority

Just like in maths, Python doesn't evaluate operators strictly left to right. Some operators are worked out **before** others, following this order of priority, from highest to lowest:

1. `**` (exponentiation) has the **highest** priority.
2. Unary `+` and `-` come next.
   - A unary operator to the **right** of `**` binds more strongly, so `4 ** -1` equals `0.25`.
3. Then `*`, `/`, and `%`.
4. Finally, binary `+` and `-` have the **lowest** priority.

This matches what I remember from school maths (similar to BODMAS/PEMDAS), just with a couple of Python-specific operators added in.

---

### Parentheses come first

Whatever is inside **parentheses** is always calculated **first**, no matter what its priority would normally be:

```python
15 - 1 * (5 * (1 + 2))
```

Working from the inside out: `1 + 2 = 3`, then `5 * 3 = 15`, then `1 * 15 = 15`, then `15 - 15 = 0`.

**Result:** `0`

---

### Exponentiation binds right to left

Most operators are worked out left to right, but `**` is the exception: it uses **right-sided binding**. That means when I chain exponents together, Python starts from the **right-hand** one:

```python
2 ** 2 ** 3
```

Python evaluates the rightmost `**` first: `2 ** 3 = 8`, then `2 ** 8 = 256`.

**Result:** `256`

This one surprised me. I expected it to work left to right like most other operators, which would have given a different answer.

---

### Section 3 summary

1. An **expression** is a combination of values, variables, and operators that evaluates to a value, for example `1 + 2`.
2. **Operators** are symbols or keywords that act on values to perform operations, for example `*` multiplies two values.
3. Python's **arithmetic operators** are `+`, `-`, `*`, `/` (classic division, always returns a float), `%` (modulus, returns the remainder), `**` (exponentiation), and `//` (floor division, rounds down).
4. A **unary operator** has one operand, like `-1` or `+3`.
5. A **binary operator** has two operands, like `4 + 5` or `12 % 5`.
6. Operators follow a **priority order**: `**` first, then unary `+`/`-`, then `*`/`/`/`%`, and finally binary `+`/`-`.
7. **Parentheses** are always calculated first, for example `15 - 1 * (5 * (1 + 2)) = 0`.
8. **Exponentiation** uses right-sided binding, so `2 ** 2 ** 3 = 256`.

---

## Section 4: Variables

### What is a variable?

A **variable** is a named place in the computer's memory where I can store a value. I like to think of it as a labelled box: the label is the variable's name, and the box holds whatever value I put in it.

A variable is **created automatically** the first time I give it a value. I don't have to do anything special beforehand.

```python
score = 10
```

Now the name `score` points to the value `10`.

---

### Naming a variable

Every variable needs a **unique name**, called an **identifier**. There are rules for what counts as a legal name:

- It can't be empty
- It must **start with a letter or an underscore** (`_`)
- After the first character, it can contain **letters, digits, and underscores**
- It **can't be a Python keyword**, which is a word that already has a special meaning in the language (like `if`, `while`, `for`, `class`, or `True`)
- Names are **case-sensitive**, so `age`, `Age`, and `AGE` are three different variables

| Legal names ✅ | Illegal names ❌ | Why it's illegal |
|---|---|---|
| `my_var` | `2fast` | Starts with a digit |
| `_count` | `my-var` | Contains a hyphen |
| `Score2` | `my var` | Contains a space |
| `agent007` | `for` | It's a Python keyword |

---

### Python doesn't need declarations

Python is a **dynamically-typed** language. That means I **don't have to declare** a variable or say what kind of value it will hold. I just use it, and Python works out the rest.

---

### The assignment operator

To give a variable a value, I use the **assignment operator**, which is the equal sign (`=`):

```python
var = 1
```

One thing that helped me: `=` in Python doesn't mean "equals" like in maths. It means **"store the value on the right into the variable on the left."**

---

### Compound assignment operators

Python also has **shortcut operators** (called compound assignment operators) for changing a variable's value without writing its name twice:

```python
var += 1          # same as: var = var + 1
var /= 5 * 2      # same as: var = var / (5 * 2)
```

Python works out the right-hand side first, and then applies the operation to the variable.

---

### Changing a variable's value

I can give an existing variable a new value with `=` or with one of the compound operators:

```python
var = 2
print(var)

var = 3
print(var)

var += 1
print(var)
```

**Output:**

```
2
3
4
```

The variable starts as `2`, is replaced with `3`, and then increased by 1 to make `4`.

---

### Combining text and variables

I can join text and variables with the `+` operator, and show the result with `print()`:

```python
var = "007"
print("Agent " + var)
```

**Output:**

```
Agent 007
```

**A mistake to avoid:** the `+` operator can only join text with text. If the variable holds a number, this causes an error:

```python
num = 7
print("Agent " + num)
```

```
TypeError: can only concatenate str (not "int") to str
```

Two ways around this are to put a comma between the items in `print()`, like `print("Agent", num)`, or to convert the number to text first (which I'll learn more about later).

---

### Section 4 summary

1. A **variable** is a named location in memory that stores a value. It's created automatically the first time I assign a value to it.
2. Every variable needs a unique **identifier**. It must begin with a letter or an underscore, can then contain letters, digits, and underscores, and can't be a Python keyword. Identifiers are **case-sensitive**.
3. Python is **dynamically typed**, so I don't need to declare variables. I assign values with the `=` operator, for example `var = 1`.
4. **Compound assignment operators** like `var += 1` or `var /= 5 * 2` are shortcuts for changing a variable's value.
5. I can assign new values to existing variables using `=` or a compound operator.
6. I can combine text and variables using `+`, and display them with `print()`, for example `print("Agent " + var)`.

---

## Section 5: Comments

### What is a comment?

A **comment** is a note I leave in my code for **human readers**. Python ignores comments completely when the program runs, so they don't change what the program does.

In Python, a comment starts with the **`#`** symbol, and it continues to the **end of that line**:

```python
# This is a comment
print("Hello!")  # This is also a comment, placed after some code
```

**Output:**

```
Hello!
```

---

### Multi-line comments and commenting out code

If I want a comment that goes over several lines, I need to put a `#` at the start of **every line**.

I can also use a comment to **switch off a piece of code** that I don't need right now, without deleting it. Here's an example that shows both:

```python
# This program prints
# an introduction to the screen.
print("Hello!")  # Invoking the print() function
# print("I'm Python.")
```

**Output:**

```
Hello!
```

The first two lines are a multi-line comment. The third line runs normally, and the last line is "commented out," so Python skips it. If I remove the `#` later, that line will run again.

---

### Use meaningful variable names

Whenever it makes sense, I should give variables **self-commenting names**, which means names that explain themselves. For example, if I'm storing the length and width of something, `length` and `width` are much better choices than `myvar1` and `myvar2`:

```python
# Hard to understand
myvar1 = 5
myvar2 = 3
myvar3 = myvar1 * myvar2

# Easy to understand
length = 5
width = 3
area = length * width
```

Both versions do exactly the same thing, but only the second one tells me what's going on.

---

### Keep comments accurate

Comments and good names help, but only if they're **correct**. Confusing variable names, or comments with wrong information, are worse than having no comments at all. For example:

```python
# Add 10 to the score
score = score - 10
```

The comment says one thing and the code does the opposite. Anyone who trusts the comment will be misled, so if I change my code, I should update the comments too.

---

### Why comments matter

- **For my future self:** I might read my own code after a few weeks and forget what it does (even experienced developers do!). Comments help me remember.
- **For other people:** if someone else reads my code, comments help them understand what the program does and how it works, much more quickly.

---

### Section 5 summary

1. **Comments** leave extra information in code for human readers. They are ignored when the program runs. In Python, a comment starts with `#` and runs to the end of the line.
2. For a comment that spans several lines, I put a `#` in front of every line. I can also use comments to **mark code that isn't needed right now**.
3. When possible, I should give variables **self-commenting names**, like `length` and `width` instead of `myvar1` and `myvar2`.
4. Comments and readable variable names make programs easier to understand, but I must avoid **confusing names** and **wrong or misleading comments**.
5. Comments are useful when I read my own code after some time, and when others read it, because they help explain what the program does and how.

---

## Section 6: The input() function

### print() vs. input()

So far I've used `print()` to make my program **talk to the user**. Now I can make it **listen** as well:

- `print()` **sends** data to the console
- `input()` **gets** data from the console

Together they let a program have a real conversation with the person using it.

---

### The prompt string

The `input()` function has an optional **parameter** called the **prompt string**. It lets me show a message to the user before they type anything:

```python
name = input("Enter your name: ")
print("Hello, " + name + ". Nice to meet you!")
```

**Sample run:**

```
Enter your name: Sam
Hello, Sam. Nice to meet you!
```

Whatever the user types is stored in the variable `name`, and then I use it in the greeting.

---

### The program waits for the user

When Python reaches `input()`, the program's flow **stops**. The cursor keeps blinking, waiting for the user to type something and press **Enter**. Nothing else happens until they do.

> 📝 **Note:** I can test this fully on my own computer. In the Edube sandbox, programs are only allowed to run for a few seconds to save resources, so if I run the code above and just wait, the sandbox will stop the program automatically. In IDLE, the program keeps waiting for as long as I like. Trying both showed me the difference.

---

### Using input() to end a program

Because `input()` pauses the program, I can use it as a way to let the user decide **when the program ends**:

```python
name = input("Enter your name: ")
print("Hello, " + name + ". Nice to meet you!")

print("\nPress Enter to end the program.")
input()
print("THE END.")
```

The `\n` at the start of the message adds a blank line. Then `input()` waits for the user to press Enter, and only after that does the program print `THE END.`

---

### input() always returns a string

This is an important one: **the result of `input()` is always a string**, even if the user types a number. That means the `+` operator **joins** the values together (concatenation) and doesn't add them up:

```python
num_1 = input("Enter the first number: ")   # Enter 12
num_2 = input("Enter the second number: ")  # Enter 21

print(num_1 + num_2)   # the program returns 1221
```

**Output:**

```
1221
```

It's `1221` and not `33`, because Python treated `12` and `21` as pieces of text and stuck them together. To do real maths with input, I'll need to convert the strings into numbers, which I'll learn about later.

---

### Replicating strings

I can also **multiply** a string by a number, which repeats it. This is called **replication**:

```python
my_input = input("Enter something: ")   # Example input: hello

print(my_input * 3)   # Expected output: hellohellohello
```

**Output:**

```
hellohellohello
```

---

### Section 6 summary

1. `print()` **sends** data to the console, while `input()` **gets** data from the console.
2. `input()` has an optional **prompt string** that shows a message before the user types, for example `name = input("Enter your name: ")`.
3. When `input()` is called, the program **stops and waits** until the user types something and/or presses Enter. This can also be used to let the user decide when a program ends.
4. The result of `input()` is always a **string**. Using `+` on strings joins them (concatenation), so `"12" + "21"` gives `1221`.
5. I can **multiply strings** with `*` to repeat them (replication), for example `"hello" * 3` gives `hellohellohello`.

---

## 💡 Module 2 Key Takeaways

- The `print()` function sends data out, and the `input()` function brings data in, so together they let a program talk with the user.
- Python has **69 built-in functions**, and I can call any of them by name, passing arguments inside parentheses.
- A **literal** is a fixed value in code, such as a number, a string, a Boolean, or `None`.
- A **variable** is a named location in memory. Python is dynamically typed, so I never need to declare one before using it.
- **Operators** combine values into **expressions**, and Python follows a clear priority order, with parentheses always calculated first.
- **Comments**, marked with `#`, and meaningful variable names make my code easier for me, and for others, to understand later.
- Whatever `input()` returns is always a **string**, even if it looks like a number, so `+` joins text rather than adding numbers.

---

##  Reflection

Module 2 felt like the point where I started actually "talking" to my programs, since `input()` and `print()` let me build something interactive for the first time. The part that surprised me most was that `input()` always returns a string, since it's easy to forget and expect numbers to just work. Learning to read the operator priority table also helped me stop guessing and start reasoning through expressions properly.

---

*Documented as part of my Python learning journey with Team Forge. Feedback and suggestions are welcome! 
