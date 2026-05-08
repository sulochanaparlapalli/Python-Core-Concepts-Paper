# Technical Paper: Python Core Concepts

---

## 1. Introduction

Python is a high-level, interpreted programming language widely used in data science, web development, automation, and analytics. This document summarizes key Python concepts including data structures, OOP, decorators, environment management, package handling, and coding standards.

---

## 2. List Methods in Python

A list in Python is a built-in mutable data structure used to store ordered collections of items.

### 🔹 Common List Methods

```python
arr = [10, 20, 30, 40]
```

### ➤ Adding elements

* append(x) → Add element at end
* insert(i, x) → Insert at index
* extend(iterable) → Add multiple elements

```python
arr.append(50)
arr.insert(1, 15)
arr.extend([60, 70])
```

### ➤ Removing elements

* remove(x) → Remove first occurrence
* pop(i) → Remove by index
* clear() → Remove all elements

```python
arr.remove(20)
arr.pop(0)
arr.clear()
```

### ➤ Utility methods

* sort() → Sort ascending
* reverse() → Reverse list
* index(x) → Find index
* count(x) → Count occurrences

```python
numbers = [3, 1, 2, 1]
numbers.sort()
print(numbers.count(1))
```
---

## 3. String Methods

Strings are immutable sequences of characters used for storing and processing text data.

```python
s = "python programming"
```

### 🔹 Common String Methods

#### ➤ Case conversion

* upper() → uppercase
* lower() → lowercase
* title() → Title Case
* capitalize() → First letter capital

```python
s.upper()
s.title()
```

#### ➤ Searching

* find(x) → returns index
* index(x) → same but raises error if not found
* count(x) → frequency
* startswith(x) → Checks prefix
* endswith(x) → Checks suffix

#### ➤ Modification Methods

* replace(a, b) → Replaces substring
* strip() → Removes whitespace
* split() → Converts string to list
* ' '.join(list) → Joins list into string

```python
sentence = "Hello World"
print(sentence.replace("World", "Python"))
```

---

## 4. Objects and Object-Oriented Programming (OOP)

Object-Oriented Programming (OOP) is a programming paradigm based on objects, which contain attributes (data) and methods (functions).

Key advantages of OOP include:

* Code reusability
* Scalability
* Modularity
* Maintainability

### ➤ 1. Class and Object

A class is a blueprint, while an object is an instance of that class.

```python
class Car:

    def __init__(self, brand, model):
        self.brand = brand
        self.model = model

    def display(self):
        print(self.brand, self.model)

c1 = Car("Toyota", "Innova")
c1.display()
``` 

### ➤ 2. Encapsulation

Encapsulation hides internal data and restricts direct access.

```python
class BankAccount:

    def __init__(self):
        self.__balance = 1000

    def get_balance(self):
        return self.__balance
```

Encapsulation improves data security by restricting direct access.

### ➤ 3. Inheritance

Inheritance allows one class to reuse features of another class.

```python
class Animal:

    def sound(self):
        print("Animal Sound")


class Dog(Animal):
    pass


d1 = Dog()
d1.sound()
```

### ➤ 4. Polymorphism

Polymorphism allows methods with the same name to behave differently.

```python
class Dog:
    def sound(self):
        print("Bark")


class Cat:
    def sound(self):
        print("Meow")

d = Dog()
c = Cat()

d.sound()
c.sound()
```

### ➤ 5. Abstraction

Abstraction hides implementation details and shows only essential features.

```python
from abc import ABC, abstractmethod


class Vehicle(ABC):

    @abstractmethod
    def start(self):
        pass


class Car(Vehicle):

    def start(self):
        print("Car starts")


c1 = Car()
c1.start()
```

Abstraction helps reduce complexity by hiding unnecessary implementation details. 

--- 

## 5. Decorators

A decorator is a function that modifies another function without changing its original code.

### Example

```python
def decorator(func):

    def wrapper():
        print("Before function")
        func()
        print("After function")

    return wrapper


@decorator
def hello():
    print("Hello World")


hello()
```

### Use Cases

* Logging
* Authentication
* Performance measurement
* Input validation

---

## 6. virtualenv

A virtual environment is an isolated Python environment used to manage dependencies separately for each project.

### Commands

* Create virtual environment

```bash
python3 -m venv venv
```

* Activate environment

```bash
source venv/bin/activate
```

* Deactivate environment

```bash
deactivate
```

---

## 7. pip Package Manager

pip is the default Python package manager used to install and manage external libraries.

* Common Commands

```bash
pip install pandas
pip uninstall pandas
pip list
pip freeze > requirements.txt
pip install -r requirements.txt
```

* Requirements File

```bash
pip freeze > requirements.txt
pip install -r requirements.txt
```

---

## 8. PEP-8 Standards Summary

PEP-8 is the official Python style guide that defines coding conventions for readability and consistency.

### Important Rules

#### ➤ Naming Conventions

* Variables/functions → snake_case
* Classes → PascalCase
* Constants → UPPER_CASE

#### ➤ Formatting Rules

* Use 4 spaces indentation
* Max line length: 79 characters
* Add spaces around operators

```python
total = 10 + 20
```

#### ➤ Imports

* One import per line
* Standard library imports first

---

## 9. Conclusion

This paper presented fundamental Python concepts including lists,
string manipulation, object-oriented programming principles,
decorators, virtual environments, package management, and coding
standards. These concepts provide a strong foundation for developing
efficient, scalable, and maintainable Python applications.

---

## 10. Key Takeaways

- Python provides simple and readable syntax
- Lists and strings support powerful built-in methods
- OOP improves scalability and maintainability
- Decorators enhance functionality dynamically
- virtualenv isolates project dependencies
- pip simplifies package management
- PEP-8 improves code readability and consistency

---

## 11. References

1. Python Official Documentation  
   https://docs.python.org/3/

2. PEP 8 – Style Guide for Python Code  
   https://peps.python.org/pep-0008/

3. Python Packaging User Guide  
   https://packaging.python.org/

4. Real Python Tutorials  
   https://realpython.com/

5. GeeksforGeeks Python Programming  
   https://www.geeksforgeeks.org/python-programming-language/

6. W3Schools Python Tutorial  
   https://www.w3schools.com/python/

7. Pandas Documentation  
   https://pandas.pydata.org/docs/
