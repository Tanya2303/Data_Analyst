# Python Data Structures - Quick Reference

A concise guide to Python's core data structures: Lists, Tuples, Sets, and Dictionaries.

---

## LISTS

### Introduction

- Ordered, mutable collection of items
- Can contain mixed data types
- Allow duplicate elements
- Denoted by square brackets `[]`

### Creating Lists

```python
empty_list = []
numbers = [1, 2, 3, 4, 5]
mixed = [1, "hello", 3.14, True]
from_range = list(range(5))  # [0, 1, 2, 3, 4]
```

### Accessing Elements

```python
fruits = ["apple", "banana", "cherry"]

print(fruits[0])    # First element: apple
print(fruits[-1])   # Last element: cherry
print(fruits[1])    # Second element: banana
```

### Modifying Lists

```python
fruits = ["apple", "banana", "cherry"]

fruits[1] = "blueberry"     # Change element
fruits.append("date")       # Add to end
fruits.insert(1, "avocado") # Insert at index
fruits.remove("apple")      # Remove by value
fruits.pop()                # Remove last element
fruits.pop(0)               # Remove by index
del fruits[0]               # Delete by index
fruits.clear()              # Remove all elements
```

### Slicing

```python
numbers = [0, 1, 2, 3, 4, 5]

print(numbers[1:4])    # [1, 2, 3] (start:stop)
print(numbers[:3])     # [0, 1, 2] (from start)
print(numbers[3:])     # [3, 4, 5] (to end)
print(numbers[::2])    # [0, 2, 4] (every 2nd element)
print(numbers[::-1])   # [5, 4, 3, 2, 1, 0] (reverse)
```

### Common Methods

```python
numbers = [3, 1, 4, 1, 5]

numbers.sort()           # Sort in place
numbers.reverse()        # Reverse in place
numbers.count(1)         # Count occurrences: 2
numbers.index(4)         # Find index of value: 2
len(numbers)             # Length: 5
numbers.extend([6, 7])   # Add multiple elements
numbers.copy()           # Create shallow copy
```

### Iteration

```python
fruits = ["apple", "banana", "cherry"]

# Simple iteration
for fruit in fruits:
    print(fruit)

# With index
for i, fruit in enumerate(fruits):
    print(f"{i}: {fruit}")
```

### List Comprehension

- Concise way to create lists from existing iterables

```python
# Basic syntax: [expression for item in iterable if condition]

squares = [x**2 for x in range(5)]           # [0, 1, 4, 9, 16]
evens = [x for x in range(10) if x % 2 == 0]  # [0, 2, 4, 6, 8]
upper = [s.upper() for s in ["a", "b", "c"]]  # ['A', 'B', 'C']
```

### Nested Lists

```python
matrix = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
]

print(matrix[0])      # [1, 2, 3]
print(matrix[1][2])   # 6
```

### Using Loops with Lists

```python
numbers = [1, 2, 3, 4, 5]

# Process each element
for num in numbers:
    print(num * 2)

# Create new list
doubled = []
for num in numbers:
    doubled.append(num * 2)

# Loop with conditions
for num in numbers:
    if num % 2 == 0:
        print(f"{num} is even")
```

---

## TUPLES

### Introduction

- Ordered, **immutable** collection
- Faster than lists
- Can contain mixed data types
- Denoted by parentheses `()` or without

### Creating Tuples

```python
empty_tuple = ()
single = (5,)              # Note the comma!
numbers = (1, 2, 3, 4, 5)
mixed = (1, "hello", 3.14)
without_parens = 1, 2, 3   # Also valid
from_list = tuple([1, 2, 3])
```

### Accessing Elements

```python
colors = ("red", "green", "blue")

print(colors[0])    # First element: red
print(colors[-1])   # Last element: blue
print(colors[1:3])  # Slicing: ('green', 'blue')
```

### Tuple Operations

```python
t1 = (1, 2, 3)
t2 = (4, 5, 6)

combined = t1 + t2         # Concatenation: (1, 2, 3, 4, 5, 6)
repeated = t1 * 2          # Repetition: (1, 2, 3, 1, 2, 3)
length = len(t1)           # Length: 3
exists = 2 in t1           # Membership: True
```

### Immutable Nature

```python
colors = ("red", "green", "blue")

# colors[0] = "yellow"  # ❌ TypeError: cannot modify

# To "modify", create new tuple
colors = ("yellow",) + colors[1:]  # ('yellow', 'green', 'blue')
```

### Tuple Methods

```python
numbers = (1, 2, 3, 2, 4, 2)

count = numbers.count(2)    # Count occurrences: 3
index = numbers.index(3)    # Find first index: 2
```

### Packing and Unpacking

```python
# Packing: creating tuple
coords = 10, 20, 30

# Unpacking: extracting values
x, y, z = coords
print(x)  # 10

# Swap variables
a, b = 1, 2
a, b = b, a  # a=2, b=1

# Extended unpacking
first, *middle, last = (1, 2, 3, 4, 5)
# first=1, middle=[2, 3, 4], last=5
```

### Nested Tuples

```python
nested = ((1, 2), (3, 4), (5, 6))

print(nested[0])      # (1, 2)
print(nested[1][1])   # 4
```

### Loops with Tuples

```python
colors = ("red", "green", "blue")

for color in colors:
    print(color)

# With enumerate
for i, color in enumerate(colors):
    print(f"{i}: {color}")
```

---

## SETS

### Introduction

- Unordered collection of **unique** elements
- Mutable (can add/remove elements)
- No duplicates allowed
- No indexing (unordered)
- Denoted by curly braces `{}` or `set()`

### Creating Sets

```python
empty_set = set()           # Must use set(), not {}
numbers = {1, 2, 3, 4, 5}
mixed = {1, "hello", 3.14}
from_list = set([1, 2, 2, 3])  # {1, 2, 3} - duplicates removed
```

### Set Operations

```python
a = {1, 2, 3, 4}
b = {3, 4, 5, 6}

# Union: all elements from both sets
print(a | b)           # {1, 2, 3, 4, 5, 6}
print(a.union(b))

# Intersection: common elements
print(a & b)           # {3, 4}
print(a.intersection(b))

# Difference: in a but not in b
print(a - b)           # {1, 2}
print(a.difference(b))

# Symmetric difference: in a or b, but not both
print(a ^ b)           # {1, 2, 5, 6}
print(a.symmetric_difference(b))
```

### Common Methods

```python
fruits = {"apple", "banana"}

fruits.add("cherry")         # Add element
fruits.update(["date", "fig"])  # Add multiple
fruits.remove("apple")       # Remove (error if not found)
fruits.discard("grape")      # Remove (no error)
fruits.pop()                 # Remove random element
fruits.clear()               # Remove all
fruits.copy()                # Shallow copy
```

### Membership Testing

- Sets provide **fastest** membership testing

```python
fruits = {"apple", "banana", "cherry"}

print("apple" in fruits)      # True (very fast)
print("grape" not in fruits)  # True
```

### Mathematical Set Operations

```python
a = {1, 2, 3}
b = {2, 3, 4}
c = {1, 2}

# Subset: all elements of c are in a
print(c.issubset(a))      # True
print(c <= a)             # True

# Superset: a contains all elements of c
print(a.issuperset(c))    # True
print(a >= c)             # True

# Disjoint: no common elements
print(a.isdisjoint(b))    # False (have 2, 3 in common)
```

---

## DICTIONARIES

### Introduction

- Unordered collection of **key-value pairs**
- Keys must be unique and immutable (strings, numbers, tuples)
- Values can be any type
- Mutable (can add/remove/modify)
- Denoted by curly braces `{}` with `key: value`

### Creating Dictionaries

```python
empty_dict = {}
person = {
    "name": "Alice",
    "age": 25,
    "city": "New York"
}

# Using dict() constructor
scores = dict(math=90, english=85, science=88)

# From list of tuples
pairs = [("a", 1), ("b", 2)]
d = dict(pairs)
```

### Accessing and Modifying Elements

```python
person = {"name": "Alice", "age": 25}

# Access
print(person["name"])        # Alice
print(person.get("age"))     # 25
print(person.get("city", "Unknown"))  # Unknown (default)

# Modify
person["age"] = 26           # Update existing
person["city"] = "Boston"    # Add new key
del person["age"]            # Delete key
removed = person.pop("city") # Remove and return value

# person["missing"]  # ❌ KeyError
```

### Common Methods

```python
person = {"name": "Alice", "age": 25, "city": "NYC"}

person.keys()              # dict_keys(['name', 'age', 'city'])
person.values()            # dict_values(['Alice', 25, 'NYC'])
person.items()             # dict_items([('name', 'Alice'), ...])

person.update({"age": 26, "job": "Engineer"})  # Update multiple
person.setdefault("country", "USA")  # Add if key doesn't exist
person.clear()             # Remove all items
person.copy()              # Shallow copy
```

### Iterating Through Dictionaries

```python
scores = {"math": 90, "english": 85, "science": 88}

# Iterate over keys
for subject in scores:
    print(subject)

# Iterate over values
for score in scores.values():
    print(score)

# Iterate over key-value pairs
for subject, score in scores.items():
    print(f"{subject}: {score}")
```

### Nested Dictionaries

```python
students = {
    "student1": {
        "name": "Alice",
        "age": 20,
        "grades": [90, 85, 88]
    },
    "student2": {
        "name": "Bob",
        "age": 22,
        "grades": [78, 82, 80]
    }
}

print(students["student1"]["name"])      # Alice
print(students["student2"]["grades"][0]) # 78
```

### Dictionary Comprehensions

```python
# Basic syntax: {key_expr: value_expr for item in iterable if condition}

squares = {x: x**2 for x in range(5)}
# {0: 0, 1: 1, 2: 4, 3: 9, 4: 16}

# Filter with condition
even_squares = {x: x**2 for x in range(10) if x % 2 == 0}
# {0: 0, 2: 4, 4: 16, 6: 36, 8: 64}

# Transform existing dict
prices = {"apple": 0.5, "banana": 0.3}
doubled = {item: price*2 for item, price in prices.items()}
```

---

## Quick Comparison

| Feature | List | Tuple | Set | Dictionary |
|---------|------|-------|-----|------------|
| **Ordered** | ✓ | ✓ | ✗ | ✗ (3.7+: insertion order) |
| **Mutable** | ✓ | ✗ | ✓ | ✓ |
| **Duplicates** | ✓ | ✓ | ✗ | Keys: ✗, Values: ✓ |
| **Indexing** | ✓ | ✓ | ✗ | By key |
| **Syntax** | `[]` | `()` | `{}` | `{k: v}` |
| **Use Case** | Ordered collections | Immutable data | Unique items, math ops | Key-value pairs |

---

## Summary

This guide covered Python's four main data structures:
- **Lists**: Mutable, ordered, allows duplicates
- **Tuples**: Immutable, ordered, faster than lists
- **Sets**: Unique elements, fast membership testing
- **Dictionaries**: Key-value pairs, fast lookups

Choose the right structure based on your needs: mutability, order, uniqueness, and access patterns.