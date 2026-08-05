
---
title: "Day4-Python"
date: 2025-07-14T22:10:00+08:00
draft: false
author: "Zack-Zhang1031"
tags: ["Python Basics"]
---
```

## Table of Contents

* Series Table of Contents
* Introduction
* I. Assignment Statements

  * 1. Basic Form
* II. Conditional Statements

  * 1. if-elif-else
  * 2. match-case
* III. Loop Statements

  * 1. for loop
  * 2. while loop
  * 3. Loop Control Statements
* Summary

---

## Introduction

This article introduces the most common **statements** in Python: assignment, conditional, and loop statements. The difference between statements and expressions is that **statements mainly perform actions and do not return values** (for example, a for loop just “operates” on a set of data, not returns a new object). Understanding these statements is the first step in writing good Python programs. **Function definitions and exception handling** will be covered separately later.

---

## I. Assignment Statements

Assignment statements are used to **bind a reference to an object**, i.e., to assign a value to a variable. Common forms include:

### 1. Basic Form

**Variable assignment**

```python
a = 4
b = a + 2
```

**Tuple or list unpacking assignment**

```python
# Tuple unpacking
(a, b) = (1, 2)
print(a, b)   # Output: 1 2

# List unpacking
[c, d] = [3, 4]
print(c, d)   # Output: 3 4
```

**Attribute assignment**

```python
class Dog:
    pass

dog1 = Dog()
dog1.weight = 10
print(dog1.weight)  # Output: 10
```

**Index assignment**

```python
# List
lst = [5, 6, 7]
lst[0] = 4
print(lst)  # [4, 6, 7]

# Dictionary
d = {'one': 1, 'two': 2}
d['one'] = '一'
print(d)  # {'one': '一', 'two': 2}
```

---

## II. Conditional Statements

Conditional statements are used to **make decisions and execute different code blocks**. The core statements are `if-elif-else` and `match-case`.

### 1. if-elif-else

#### 1.1 Form

```python
if condition1:
    block1
elif condition2:
    block2
else:
    block3
```

#### 1.2 Example

**Grading**

```python
score = 85
if score >= 90:
    print("Excellent")
elif score >= 60:
    print("Pass")
else:
    print("Fail")
```

Output: Pass

---

### 2. match-case (Python 3.10+)

Best for situations with **multiple options**, and clearer than multiple `if-elif-else` statements.

#### 2.1 Form

```python
match expression:
    case pattern1:
        block1
    case pattern2:
        block2
    case _:
        default block
```

#### 2.2 Example

**Command status judgment**

```python
command = "start"
match command:
    case "start":
        print("Start the program")
    case "stop":
        print("Stop the program")
    case _:
        print("Unknown command")
```

Output: Start the program

---

## III. Loop Statements

Loop statements are used to **repeat certain operations**, mainly `for` and `while` loops.

### 1. for loop

Used for iterating over iterable objects such as list, str, dict, etc.

#### 1.1 Form

```python
for variable in iterable:
    block
```

#### 1.2 Example

**Counting the number of each character in a string**

```python
text = "hello world"
letter_count = {}
for char in text:
    if char.isalpha():
        char = char.lower()
        letter_count[char] = letter_count.get(char, 0) + 1
print(letter_count)
# Output: {'h': 1, 'e': 1, 'l': 3, 'o': 2, 'w': 1, 'r': 1, 'd': 1}
```

---

### 2. while loop

Used for **unknown number of iterations**, runs as long as the condition is true.

#### 2.1 Form

```python
while condition:
    block
```

#### 2.2 Example

**Login validation: up to three attempts**

```python
correct_username = "admin"
correct_password = "123456"
attempts = 0
max_attempts = 3

while True:
    username = input("Please enter username: ")
    password = input("Please enter password: ")
    attempts += 1
    if username == correct_username and password == correct_password:
        print("Login successful!")
        break
    else:
        print("Incorrect username or password.")
    if attempts >= max_attempts:
        print("Too many attempts, account locked.")
        break
```

---

### 3. Loop Control Statements

#### break — terminates the loop

```python
for i in range(10):
    if i == 3:
        break
    print(i)  # Output: 0 1 2
```

#### continue — skips to the next iteration

```python
for i in range(5):
    if i == 2:
        continue
    print(i)  # Output: 0 1 3 4
```

#### pass — does nothing, just a placeholder (optional to know)

```python
for i in range(3):
    if i == 1:
        pass  # Does nothing here
    print(i)
# Output: 0 1 2
```

---

## Summary

* **Statements** are the most basic action units in Python, and do not directly return a value. Distinguish "statements" from "expressions".
* Master various forms of **assignment statements** for flexible variable/object binding and unpacking.
* Proficiently use **conditional statements** (`if-elif-else` and `match-case`) for branching logic.
* Understand the differences and scenarios for **for** and **while** loops, and how to use `break` and `continue` for control.
* Further learning will include functions, exception handling, and more advanced topics.

---

**Recommended Reading:**

* [Python official docs: Control Flow](https://docs.python.org/3/tutorial/controlflow.html)
* [Liao Xuefeng's Python Tutorial: Conditionals and Loops](https://www.liaoxuefeng.com/wiki/1016959663602400/1017261630425888)

---
