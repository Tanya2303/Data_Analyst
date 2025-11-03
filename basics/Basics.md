# Python Basics - Quick Reference Guide

A beginner-friendly guide covering fundamental Python programming concepts.

---

## Syntax

**Syntax** refers to the set of rules that defines how Python code must be written.

- Python uses simple, readable syntax similar to English
- Statements typically end with a newline (no semicolons required)
- Code blocks are defined by indentation, not braces

```python
print("Hello, World!")  # Valid syntax
```

---

## Semantics

**Semantics** refers to the meaning of the code - what it actually does when executed.

- Syntax = Structure (how to write)
- Semantics = Meaning (what it does)

```python
x = 5 + 3  # Syntax: correct structure | Semantics: adds 5 and 3, stores result in x
```

---

## Case Sensitivity

Python is **case-sensitive** - uppercase and lowercase letters are treated as different.

```python
name = "Alice"
Name = "Bob"
NAME = "Charlie"
# These are three different variables!
```

---

## Indentation

Indentation (whitespace at the start of a line) is **required** to define code blocks.

- Use 4 spaces per indentation level (recommended)
- Mixing tabs and spaces causes errors

```python
if True:
    print("Correct indentation")  # 4 spaces
    print("Same block")

# if True:
# print("Error!")  # No indentation = error
```

---

## Comments

Comments are notes in code ignored by Python.

**Single-line comments** use `#`:
```python
# This is a comment
x = 10  # Inline comment
```

**Multi-line comments** use triple quotes:
```python
"""
This is a multi-line comment
or docstring
"""
```

---

## Line Continuation

Break long lines using backslash `\` or implicit continuation inside parentheses.

```python
# Using backslash
total = 1 + 2 + 3 + \
        4 + 5

# Using parentheses (preferred)
total = (1 + 2 + 3 +
         4 + 5)
```

---

## Variables

### Declaring and Assigning

Variables store data values. No declaration needed - just assign!

```python
x = 5          # Integer
name = "John"  # String
is_valid = True  # Boolean
```

### Printing Variables

```python
age = 25
print(age)                    # Output: 25
print("Age:", age)            # Output: Age: 25
print(f"Age is {age}")        # Output: Age is 25 (f-string)
```

### Naming Conventions

- Use lowercase with underscores: `my_variable`
- Start with letter or underscore: `_private`, `data1`
- Cannot start with number: ~~`1data`~~ ❌
- Avoid reserved keywords: ~~`class`, `if`, `for`~~ ❌
- Use descriptive names: `student_count` > `sc`

---

## Data Types

Common built-in data types:

```python
# Numeric
integer = 42                    # int
decimal = 3.14                  # float
complex_num = 2 + 3j            # complex

# Text
text = "Hello"                  # str

# Boolean
is_true = True                  # bool
is_false = False

# Collections
my_list = [1, 2, 3]            # list
my_tuple = (1, 2, 3)           # tuple
my_dict = {"key": "value"}     # dict
my_set = {1, 2, 3}             # set
```

### Type Conversion

Convert between data types explicitly:

```python
x = "10"
y = int(x)        # String to integer: 10
z = float(x)      # String to float: 10.0

a = 5
b = str(a)        # Integer to string: "5"

c = bool(0)       # Any type to boolean: False
d = bool(10)      # Non-zero = True
```

---

## Dynamic Typing

Python automatically determines variable types - you can reassign different types.

```python
x = 10          # x is int
print(type(x))  # <class 'int'>

x = "Hello"     # Now x is str
print(type(x))  # <class 'str'>
```

---

## Input

Get user input using `input()` function (always returns a string):

```python
name = input("Enter your name: ")
print(f"Hello, {name}!")

# Convert input to numbers
age = int(input("Enter age: "))
height = float(input("Enter height: "))
```

---

## Operators

### Arithmetic Operators

```python
a, b = 10, 3

print(a + b)   # Addition: 13
print(a - b)   # Subtraction: 7
print(a * b)   # Multiplication: 30
print(a / b)   # Division: 3.333...
print(a // b)  # Floor division: 3
print(a % b)   # Modulus (remainder): 1
print(a ** b)  # Exponentiation: 1000
```

### Comparison Operators

Return `True` or `False`:

```python
x, y = 5, 10

print(x == y)  # Equal: False
print(x != y)  # Not equal: True
print(x < y)   # Less than: True
print(x > y)   # Greater than: False
print(x <= y)  # Less than or equal: True
print(x >= y)  # Greater than or equal: False
```

### Logical Operators

Combine boolean expressions:

```python
a, b = True, False

print(a and b)  # AND: False
print(a or b)   # OR: True
print(not a)    # NOT: False

# Example
age = 25
if age >= 18 and age < 65:
    print("Working age")
```

---

## Control Flow

Control the order of code execution.

---

## Conditional Statements

### if Statement

```python
age = 20

if age >= 18:
    print("Adult")
```

### if-else Statement

```python
age = 15

if age >= 18:
    print("Adult")
else:
    print("Minor")
```

### if-elif-else Statement

```python
score = 85

if score >= 90:
    print("A")
elif score >= 80:
    print("B")
elif score >= 70:
    print("C")
else:
    print("F")
```

### Nested Conditionals

```python
age = 20
has_license = True

if age >= 18:
    if has_license:
        print("Can drive")
    else:
        print("Need license")
else:
    print("Too young")
```

---

## Loops

### for Loop

Iterate over sequences (lists, strings, ranges):

```python
# Loop through range
for i in range(5):
    print(i)  # 0, 1, 2, 3, 4

# Loop through list
fruits = ["apple", "banana", "cherry"]
for fruit in fruits:
    print(fruit)

# Loop through string
for char in "Python":
    print(char)
```

### while Loop

Repeat while condition is true:

```python
count = 0
while count < 5:
    print(count)
    count += 1

# Infinite loop (use with caution!)
# while True:
#     print("Forever")
```

### break Statement

Exit loop immediately:

```python
for i in range(10):
    if i == 5:
        break
    print(i)  # 0, 1, 2, 3, 4
```

### continue Statement

Skip to next iteration:

```python
for i in range(5):
    if i == 2:
        continue
    print(i)  # 0, 1, 3, 4 (skips 2)
```

### pass Statement

Placeholder that does nothing:

```python
for i in range(5):
    if i == 2:
        pass  # Do nothing, continue
    print(i)  # 0, 1, 2, 3, 4
```

### Nested Loops

```python
# Multiplication table
for i in range(1, 4):
    for j in range(1, 4):
        print(f"{i} x {j} = {i*j}")
```

---

## Summary

This guide covers Python fundamentals including:
- Basic syntax and semantics
- Variables, data types, and operators
- User input and type conversion
- Control flow with conditionals
- Loops and loop control statements
