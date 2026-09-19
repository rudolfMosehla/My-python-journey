#  My Python Journey: Module 1 Recap

## Introduction to Python and Computer Programming

**Team:** Forge 🔥
**Course:** Cisco Networking Academy, Python Essentials 1 (Module 1)

Module 1 answers three big questions before we write real code: **How does a computer run a program? What's the difference between compiling and interpreting? And what exactly is Python?** This is my documentation of what I learned.

---

## 📚 Table of Contents

**Getting started with the course**

- [Learn Python: the language of today and tomorrow](#learn-python-the-language-of-today-and-tomorrow)
- [About the course](#about-the-course)
- [Syllabus](#syllabus)
- [Preparing for the PCEP exam](#preparing-for-the-pcep-exam)

**The fundamentals of computer programming**

- [1.1.1 How does a computer program work?](#111-how-does-a-computer-program-work)
- [1.1.2 Natural languages vs. programming languages](#112-natural-languages-vs-programming-languages)
- [1.1.3 What makes a language?](#113-what-makes-a-language)
- [1.1.4 Machine language vs. high-level language](#114-machine-language-vs-high-level-language)
- [1.1.5 Compilation vs. Interpretation](#115-compilation-vs-interpretation)
- [1.1.6 What does the interpreter do?](#116-what-does-the-interpreter-do)
- [1.1.7 Compilation vs. Interpretation: Advantages and Disadvantages](#117-compilation-vs-interpretation-advantages-and-disadvantages)

**Introduction to Python**

- [1.2.1 Python: a tool, not a reptile](#121-python-a-tool-not-a-reptile)
- [1.2.2 Who created Python?](#122-who-created-python)
- [1.2.3 A hobby programming project](#123-a-hobby-programming-project)
- [1.2.4 What makes Python so special?](#124-what-makes-python-so-special)
- [1.2.5 Python rivals?](#125-python-rivals)
- [1.2.6 Where can we see Python in action?](#126-where-can-we-see-python-in-action)
- [1.2.7 Why not Python?](#127-why-not-python)
- [1.2.8 There is more than one Python](#128-there-is-more-than-one-python)
- [1.2.9 Python implementations](#129-python-implementations)

**Setting up and writing my first code**

- [1.3.1 Begin your Python journey](#131-begin-your-python-journey)
- [1.3.2 How to download, install, and configure Python](#132-how-to-download-install-and-configure-python)
- [1.3.3 Starting your work with Python](#133-starting-your-work-with-python)
- [1.3.4 Your very first program before your first program...](#134-your-very-first-program-before-your-first-program)
- [1.3.5 How to spoil and fix your code](#135-how-to-spoil-and-fix-your-code)
- [Key takeaways](#-key-takeaways)

---

## 🚀 Getting Started with the Course

### Learn Python: the language of today and tomorrow

Before diving into how computers work, the course starts by answering a simple question: **why learn Python at all?**

Python is one of the most popular programming languages in the world, and it keeps growing. What I took from this part is that Python is useful **today** and will stay useful **tomorrow**, because it is used in so many areas:

- Web development and automation
- Data analysis and data science
- Artificial intelligence and machine learning
- Networking, cybersecurity, and IoT

It's also friendly for beginners, since the code is easy to read, and it has a huge community to learn from. That makes it a great first language, and a language that can still take me far in my career.

### About the course

This is **Python Essentials 1**, a course from the Cisco Networking Academy that was developed by the **OpenEDG Python Institute**. A few things I learned about it:

- It's designed for **beginners**, so no earlier programming experience is needed.
- It teaches the basics of Python **and** general programming ideas, not only the language itself.
- It focuses on the **procedural** way of programming, where we give the computer a clear series of steps to follow.
- By the end, I should be able to **install my own Python environment**, use important parts of the **Python Standard Library**, and **design, write, test, and debug** simple Python programs.
- It uses hands-on practice, quizzes, and assessments, so it's about *doing* and not only reading.

### Syllabus

The course is split into **four modules**:

| Module | What it covers |
|---|---|
| **Module 1** | Introduction to Python and computer programming |
| **Module 2** | Data types, variables, basic input/output, and basic operators |
| **Module 3** | Boolean values, conditional execution, loops, lists and list processing, logical and bitwise operations |
| **Module 4** | Functions, tuples, dictionaries, exceptions, and data processing |

I'm now in **Module 1**, which lays the foundation: how computers run programs, how Python fits in, and how to write a first program. Everything after this builds on it, so I want to understand it well before moving on.

### Preparing for the PCEP exam

The course is lined up with the **PCEP – Certified Entry-Level Python Programmer** certification from the Python Institute. That means the things I learn here also prepare me for an entry-level certificate that I can show to employers and use to prove my Python skills.

---

## 📖 The Fundamentals of Computer Programming

### 1.1.1 How does a computer program work?

A computer on its own is just an object. It only becomes useful when a **program** tells it what to do. Think of a piano: without a player, it's just a wooden box.

The surprising part is that computers are actually quite "simple." They can only perform very basic operations (like adding or dividing), but they do it **extremely fast** and can repeat it as many times as needed.

#### Example: average speed of a journey

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

### 1.1.2 Natural languages vs. programming languages

A **language** is a tool for expressing and recording thoughts. Humans use natural languages (English, Yoruba, French...) and even body language. Computers have their own language too: **machine language**.

- A computer has no intelligence of its own. I like to think of it as a very well-trained dog: it only responds to a fixed set of commands it already knows.
- That full set of commands is called an **instruction list (IL)**. Different computers can have completely different ILs.
- Machine languages are **created by humans**. Natural languages, on the other hand, **evolve on their own**, with new words appearing and old ones disappearing all the time.

---

### 1.1.3 What makes a language?

Every language, whether machine or natural, is made up of four elements:

| Element | Meaning |
|---|---|
| **Alphabet** | The set of symbols the language is built from |
| **Lexis** | The vocabulary (the dictionary) of the language |
| **Syntax** | The rules for putting words together correctly |
| **Semantics** | The meaning: the program has to actually make sense |

---

### 1.1.4 Machine language vs. high-level language

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

### 1.1.5 Compilation vs. Interpretation

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

### 1.1.6 What does the interpreter do?

A program is really just a piece of **plain text** (no fonts, colours, or images), stored in a source file. When we run it, the interpreter:

1. **Reads** the code from top to bottom and left to right (there are a few exceptions we'll meet later)
2. **Checks** that each line is correct, using the four aspects above
3. **Executes** the line if it looks good

This read → check → execute cycle repeats, and some lines may run more than once.

#### Things worth remembering

- If the interpreter finds an error, it **stops immediately** and shows an error message.
- Error messages can sometimes be **misleading**. The interpreter can't read your mind, so it may report the problem *away* from where it actually started. For example, if you use a name that was never introduced, the error appears where you *use* it, but the real cause is earlier, where you should have introduced it.
- A big part of your program may run successfully **before** an error is found. That's completely normal for an interpreter.

There's no clear winner between compiling and interpreting. Both have advantages and disadvantages, which is why both still exist today.

---

### 1.1.7 Compilation vs. Interpretation: Advantages and Disadvantages

Neither model is "the best." Each one has strengths and weaknesses, which is why both still exist.

#### Compilation

**Advantages**
- The compiled program usually **runs faster**, because the translation was already done.
- Users only receive the compiled file, so the **source code stays private**.

**Disadvantages**
- The compilation step itself **can take time**, and it has to be **repeated after every change**.
- The compiled file only works on the kind of system it was made for, so you need **a different version for each platform**.

#### Interpretation

**Advantages**
- You can **run your code straight away**, with no separate compile step, which is great for testing small pieces.
- It's **portable**: the same source code works on any computer that has the right interpreter.

**Disadvantages**
- Programs usually **run slower**, because the code is translated as it runs.
- You have to share the **source code** itself, and the user must have the **interpreter installed**.

#### What this means for me

Python is an **interpreted language**, so it gets all of these advantages and disadvantages, plus a few features of its own. To run Python code I need the **Python interpreter**, and luckily **Python is free**.

---

## 🐍 Introduction to Python

### 1.2.1 Python: a tool, not a reptile

When I first heard "Python," I thought of the snake too. 😄 But in programming, **Python is a tool**: a programming language we use to tell computers what to do. The snake logo is just a mascot. The name actually comes from a British comedy show, *Monty Python's Flying Circus*.

---

### 1.2.2 Who created Python?

Python was created by **Guido van Rossum**, a Dutch programmer. He wanted a language that was powerful but still simple and pleasant to read and write.

---

### 1.2.3 A hobby programming project

What I found interesting is that Python started as a **hobby project**. Guido began working on it in the late 1980s while looking for something to keep him busy over the holidays, and the first public release came out in **1991**.

It went from a small personal project to one of the most popular languages in the world, which shows how far a good idea can go.

---

### 1.2.4 What makes Python so special?

Python has a lot going for it:

- **Easy to learn:** it takes less time to get started than with many other languages
- **Easy to read and understand:** the code looks close to plain English
- **Easy to use and teach:** which is why it's such a popular first language
- **Easy to get:** it's **free** and open source
- **Fast to write:** you can do a lot with just a few lines of code
- **Portable:** the same code can run on Windows, macOS, and Linux
- **Supported by a huge community** and many ready-made libraries

---

### 1.2.5 Python rivals?

Python isn't the only language in its space. In the world of scripting languages, its main competitors have been **Perl** and **Ruby**, and depending on the job, languages like **Java** and **JavaScript** also compete for the same work.

What keeps Python strong is its **simple, readable style** and its **large ecosystem of tools and libraries**.

---

### 1.2.6 Where can we see Python in action?

Python is used almost everywhere, often without us noticing:

- **Websites and internet services:** big names like Google, YouTube, Instagram, and Dropbox use it in parts of their systems
- **Data science and artificial intelligence:** analysing data and building machine learning models
- **Automation:** doing repetitive tasks so people don't have to
- **Networking and IT:** managing and testing networks and infrastructure, which fits well with a Cisco course
- **Small devices and hobby projects:** such as the Raspberry Pi

---

### 1.2.7 Why not Python?

Python is great, but it isn't perfect for everything. It is usually **slower** than compiled languages, so it isn't the first choice for:

- **Low-level programming**, like operating system components or device drivers
- **Very high-performance or real-time systems**
- **Native mobile apps**

Knowing a tool's limits is just as important as knowing its strengths.

---

### 1.2.8 There is more than one Python

There are two main versions of the language:

- **Python 2:** the older version, which is now **retired and no longer supported**
- **Python 3:** the modern version, released in 2008, and the one we use

They are **not fully compatible** with each other. A small example is the `print` command:

```python
print "Hello"      # Python 2 (old style)
print("Hello")     # Python 3 (what we use)
```

As a beginner, I should always make sure I'm learning and installing **Python 3**.

---

### 1.2.9 Python implementations

The Python *language* is one thing, and the programs that actually run it are another. These programs are called **implementations**, and there is more than one:

| Implementation | What it's about |
|---|---|
| **CPython** | The standard, most widely used version (written in C) |
| **Cython** | Translates Python-like code into C for extra speed |
| **Jython** | Runs Python inside the Java Virtual Machine |
| **PyPy** | A faster interpreter that uses just-in-time compilation |
| **MicroPython** | A small version for microcontrollers and tiny devices |

The code we write stays the same in spirit. What changes is where and how it runs.

---

## 💻 Setting Up and Writing My First Code

### 1.3.1 Begin your Python journey

Now that I understand how programs and interpreters work, it's time to start using Python for real. To do that I need two things:

1. The **Python interpreter**, which reads and runs my code
2. A place to **write my code**, such as an editor, or an online tool

There are two main ways to get started:

- **Install Python on my own computer**, and use its built-in editor (IDLE) or another editor
- **Use an online sandbox** (the course provides one, called Edube) to write and run code in the browser, with nothing to install

Both work, and it's good to know how to do both.

---

### 1.3.2 How to download, install, and configure Python

Here's the basic process for installing Python on my own computer:

1. Go to the official website, [python.org/downloads](https://www.python.org/downloads/)
2. Download the latest **Python 3** version for my operating system (Windows, macOS, or Linux)
3. Run the installer
4. **On Windows, tick the box that says "Add Python to PATH"** before installing, so the computer can find Python from the terminal
5. Finish the installation

To check that it worked, I can open a terminal (or Command Prompt) and run:

```bash
python --version
```

On some systems the command is `python3 --version`. If I see a version number that starts with 3, Python is ready. ✅

---

### 1.3.3 Starting your work with Python

Once Python is installed, I can use it in two ways:

- **Interactive mode:** I type a line of code at the `>>>` prompt and Python runs it immediately. It's great for testing small ideas.
- **Script mode:** I write my code in a file, save it with a `.py` ending (for example `hello.py`), and run the whole file.

Using **IDLE**, the editor that comes with Python, the basic steps are:

1. Open IDLE
2. Go to **File → New File** to open a blank editor
3. Type my code
4. Save the file with a `.py` ending
5. Run it from the **Run** menu, or by pressing **F5**

This connects to what I learned earlier: a Python program is just **plain text** saved in a source file, and the interpreter reads it from top to bottom.

---

### 1.3.4 Your very first program before your first program...

Every programmer starts with the same tradition: making the computer say hello.

```python
print("Hello, World!")
```

**Output:**

```
Hello, World!
```

Here's what's happening:

- `print` is a built-in **function** that displays something on the screen
- The **parentheses** `( )` hold what I want to display
- The **quotation marks** `" "` tell Python that the content is text, called a **string**
- Python reads the line, checks it, and executes it, just like the interpreter cycle from 1.1.6

It's only one line, but it's a real program, and it proves that my setup works. 🎉

---

### 1.3.5 How to spoil and fix your code

Now for the fun part: breaking things on purpose. Because Python is interpreted, it tells me as soon as it finds a problem, and reading these messages is a skill I need to build.

**A typo in the function name:**

```python
pront("Hello, World!")
```

```
NameError: name 'pront' is not defined
```

Python doesn't know what `pront` is, because it doesn't exist. **Fix:** spell it `print`.

**A missing closing quote:**

```python
print("Hello, World!)
```

```
SyntaxError: unterminated string literal
```

The text was opened but never closed. **Fix:** add the closing quotation mark.

**Missing parentheses (the Python 2 habit):**

```python
print "Hello, World!"
```

```
SyntaxError: Missing parentheses in call to 'print'. Did you mean print(...)?
```

This is the Python 2 style from 1.2.8, and it doesn't work in Python 3. **Fix:** use parentheses.

(The exact wording of these messages can differ a little between Python versions.)

**How I fix errors:**

1. Read the error message, especially the **last line**, which names the type of error
2. Look at the **line number** it points to
3. Remember from 1.1.6 that the real cause can sometimes be **a little earlier** than the reported line
4. Fix it and run again

Errors aren't failures. They're how Python helps me learn. 

---

## 💡 Key Takeaways

- A computer is only as useful as the program it runs, and it can only do very simple operations, very fast.
- Every language has an **alphabet, lexis, syntax, and semantics**.
- **High-level languages** are the bridge between human thinking and machine code.
- **Compilers** translate once; **interpreters** translate every time the code runs.
- Compiled programs tend to be faster and keep the source private; interpreted programs are more flexible and portable, but slower.
- Python is **interpreted, free, and beginner-friendly**, and we use **Python 3**.
- Python was created by **Guido van Rossum** as a hobby project, and it grew into one of the world's most popular languages.
- Python is great for many things, but not for everything, so it's worth knowing its limits too.
- `print()` is how I make my program talk back to me.
- I can run Python code in **interactive mode** for quick tests, or in **script mode** by saving a `.py` file.
- Python's error messages, like `NameError` and `SyntaxError`, are clues that help me fix my code, not signs that I've failed.
- When debugging, the real cause of an error is often a little **earlier** than where the interpreter reports it.

---

## 🚀 What's Next

- Module 2
  
## Reflection

This module changed how I see programming. I used to think of computers as "smart," but really they're fast and obedient, and my job as a programmer is to give them clear, correct instructions. Understanding the difference between compiling and interpreting also helps explain *why* Python behaves the way it does.

---

*Documented as part of my Python learning journey with Team Forge. Feedback and suggestions are welcome!
