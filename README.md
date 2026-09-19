# 🐍 My Python Journey: Module 1 Recap

## Introduction to Python and Computer Programming

**Team:** Forge 🔥
**Course:** Cisco Networking Academy, Python Essentials 1 (Module 1)

Module 1 answers three big questions before we write real code: **How does a computer run a program? What's the difference between compiling and interpreting? And what exactly is Python?** This is my documentation of what I learned.

---

## 📚 Table of Contents

1. [What is a program?](#1-what-is-a-program)
2. [Natural languages vs. machine languages](#2-natural-languages-vs-machine-languages)
3. [What makes a language?](#3-what-makes-a-language)
4. [High-level languages and source code](#4-high-level-languages-and-source-code)
5. [Compilation vs. interpretation](#5-compilation-vs-interpretation)
6. [What does the interpreter do?](#6-what-does-the-interpreter-do)
7. [Meet Python](#7-meet-python)
8. [Python versions and implementations](#8-python-versions-and-implementations)
9. [Setting up my environment](#9-setting-up-my-environment)
10. [My first program](#10-my-first-program)
11. [Key takeaways](#-key-takeaways)

---

## 1. What is a program?

A computer on its own is just an object. It only becomes useful when a **program** tells it what to do. Think of a piano: without a player, it's just a wooden box.

The surprising part is that computers are actually quite "simple." They can only perform very basic operations (like adding or dividing), but they do it **extremely fast** and can repeat it as many times as needed.

### Example: average speed of a journey

A computer doesn't know what "distance," "time," or "speed" mean. So we have to spell out the steps:

1. Accept a number for the distance
2. Accept a number for the travel time
3. Divide distance by time and store the result in memory
4. Display the result in a readable format

Those four steps are a program. Here's roughly what they look like in Python (a small preview of what's coming 👀):

```python
# 1 & 2. Accept the distance and time
distance = float(input("Distance (km): "))
time = float(input("Time (hours): "))

# 3. Divide and store the result
speed = distance / time

# 4. Display the result
print("Average speed:", speed, "km/h")
```

---

## 2. Natural languages vs. machine languages

A **language** is a tool for expressing and recording thoughts. Humans use natural languages (English, Yoruba, French...) and even body language. Computers have their own language too: **machine language**.

- A computer has no intelligence of its own. I like to think of it as a very well-trained dog: it only responds to a fixed set of commands it already knows.
- That full set of commands is called an **instruction list (IL)**. Different computers can have completely different ILs.
- Machine languages are **created by humans**. Natural languages, on the other hand, **evolve on their own**, with new words appearing and old ones disappearing all the time.

---

## 3. What makes a language?

Every language, whether machine or natural, is made up of four elements:

| Element | Meaning |
|---|---|
| **Alphabet** | The set of symbols the language is built from |
| **Lexis** | The vocabulary (the dictionary) of the language |
| **Syntax** | The rules for putting words together correctly |
| **Semantics** | The meaning: the program has to actually make sense |

---

## 4. High-level languages and source code

The IL is basically the **alphabet of machine language**: the simplest set of symbols for commanding a computer. But it's very far from how humans think.

We need a bridge between humans and computers. That bridge is a **high-level programming language**. These languages:

- Use words, symbols, and conventions that humans can read
- Let us express much more complex commands than a raw IL allows
- Are simpler than natural language but far richer than machine language

Some important terms:

- **Source code**: a program written in a high-level language
- **Source file**: the file that contains the source code
- **Machine code**: what the computer actually executes

---

## 5. Compilation vs. interpretation

Programming means arranging the elements of a language in the right order to get the effect you want. To be correct, a program must be right in four ways:

- **Alphabetically**: written in a script the language recognises
- **Lexically**: uses valid words from the language's dictionary
- **Syntactically**: follows the language's rules
- **Semantically**: makes sense

Mistakes in any of these can make a program useless.

Since computers only understand machine language, our high-level code has to be translated. There are two ways to do it:

| | **Compilation** | **Interpretation** |
|---|---|---|
| **How it works** | The source code is translated **once** into a machine-code file (e.g. an `.exe`) | The source code is translated **every time** the program runs |
| **Tool used** | A **compiler** | An **interpreter** |
| **Re-translation** | Needed each time you change the source code | Happens automatically on every run |
| **Distributing your program** | You can share the compiled file directly | Users need the interpreter installed too, so you can't just share the source code as-is |

A language is usually designed to be **either compiled or interpreted**. Very few can do both.

---

## 6. What does the interpreter do?

A program is really just a piece of **plain text** (no fonts, colours, or images), stored in a source file. When we run it, the interpreter:

1. **Reads** the code from top to bottom and left to right (there are a few exceptions we'll meet later)
2. **Checks** that each line is correct, using the four aspects above
3. **Executes** the line if it looks good

This read → check → execute cycle repeats, and some lines may run more than once.

### Things worth remembering

- If the interpreter finds an error, it **stops immediately** and shows an error message.
- Error messages can sometimes be **misleading**. The interpreter can't read your mind, so it may report the problem *away* from where it actually started. For example, if you use a name that was never introduced, the error appears where you *use* it, but the real cause is earlier, where you should have introduced it.
- A big part of your program may run successfully **before** an error is found. That's completely normal for an interpreter.

There's no clear winner between compiling and interpreting. Both have advantages and disadvantages, which is why both still exist today.

---

## 7. Meet Python

- **Python is an interpreted language**, so it has all the advantages and disadvantages of interpretation, plus a few features of its own.
- Interpreted languages are often called **scripting languages**, and their programs are called **scripts**.
- Python was created by **Guido van Rossum** and first released in **1991**. The name comes from the comedy show *Monty Python's Flying Circus*, not the snake 🐍😄
- Python is popular because it is:
  - **Easy to learn and read**: the code looks close to plain English
  - **Free** and open source
  - **Versatile**: used in web development, data science, automation, AI, networking, and more
  - **Supported by a huge community** and a rich standard library

---

## 8. Python versions and implementations

### Python 2 vs. Python 3

- Python 3 is the modern version, and it is **not fully backward compatible** with Python 2.
- Python 2 is retired and no longer supported, so new learners (like me) should use **Python 3**.
- One small example of a difference is the `print` statement:

```python
print "Hello"      # Python 2 (old style)
print("Hello")     # Python 3 (what we use)
```

### One language, several implementations

The Python *language* is the same, but there are different programs that run it:

| Implementation | What it's about |
|---|---|
| **CPython** | The standard, most widely used version (written in C) |
| **Cython** | Translates Python-like code into C for extra speed |
| **Jython** | Runs Python inside the Java Virtual Machine |
| **PyPy** | A faster interpreter that uses just-in-time compilation |
| **MicroPython** | A small version for microcontrollers and tiny devices |

---

## 9. Setting up my environment

To write and run Python I need the **Python interpreter** installed. There are a few ways to start:

1. **Install Python** from [python.org](https://www.python.org/downloads/) and use the built-in editor called **IDLE**
2. Use an **online sandbox** (the course provides the Edube sandbox) to run code in the browser without installing anything
3. Later, move to a full editor such as VS Code or PyCharm

To check that Python is installed, I can open a terminal and run:

```bash
python --version
```

(On some systems the command is `python3 --version`.)

---

## 10. My first program

The classic first program prints a message on the screen using the **`print()` function**:

```python
print("Hello, World!")
```

**Output:**

```
Hello, World!
```

What's happening here:

- `print` is a built-in **function** that displays something on the screen
- The text goes inside **parentheses** and **quotation marks**
- Text inside quotes is called a **string**

### Errors are my friends 🐞

Because Python is interpreted, it tells me right away when something is wrong:

```python
pront("Hello, World!")   # NameError: 'pront' is not defined (typo in the function name)
print("Hello, World!)    # SyntaxError: the string was never closed
```

Reading the error message, and remembering that the real cause may be a little earlier than the reported line, is a key skill.

---

## 💡 Key Takeaways

- A computer is only as useful as the program it runs, and it can only do very simple operations, very fast.
- Every language has an **alphabet, lexis, syntax, and semantics**.
- **High-level languages** are the bridge between human thinking and machine code.
- **Compilers** translate once; **interpreters** translate every time the code runs.
- Python is **interpreted, free, and beginner-friendly**, and we use **Python 3**.
- `print()` is how I make my program talk back to me.
- When debugging, the real cause of an error is often a little **earlier** than where the interpreter reports it.

---

## 🚀 What's Next

- Module 2: data types, variables, basic input/output, and operators
- Practise writing small programs every day
- Get comfortable reading error messages and tracing them back to their real cause

---

## 🙌 Reflection

This module changed how I see programming. I used to think of computers as "smart," but really they're fast and obedient, and my job as a programmer is to give them clear, correct instructions. Understanding the difference between compiling and interpreting also helps explain *why* Python behaves the way it does.

---

*Documented as part of my Python learning journey with Team Forge. Feedback and suggestions are welcome! 🌟*
