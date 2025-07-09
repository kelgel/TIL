# 2025-07-01 Python Basics: Conditionals, Loops, Classes, and Built-in Functions

## What I Did Today

- Studied core Python syntax: `if`, `for` loops, functions, classes, and how to use libraries  
- Solved basic programming exercises to apply what I learned  
- Practiced writing Python classes and explored the purpose of `self`  
- Compared class behavior between Python and Java to better understand the differences

---

## What I Learned

- ### Python Control Flow & Core Syntax

- Used `if`, `elif`, and `else` to write conditional logic  
- Practiced `for` loops for iterating over strings, ranges, and lists  
- Learned how to define and call functions, and used built-in functions like `len()`, `type()`, and `range()`  
- Imported and used standard libraries like `math` and `random`  

- ### Python Classes & Why `self` Matters

- In Python, every instance method must have `self` as the first parameter  
- `self` is used to access instance variables and other methods in the class  
- Without `self`, variables are treated as local to the method and not associated with the object  

- #### ✅ Example:

```python
class Dog:
    def __init__(self, name):
        self.name = name

    def bark(self):
        print(f"{self.name} barks: Woof!")
```
- ### 🔄 Python vs. Java – Class Structure Confusion
| Concept           | Java                             | Python                          |
| ----------------- | -------------------------------- | ------------------------------- |
| `this` / `self`   | `this` is optional/implicit      | `self` is explicit and required |
| Constructor       | Named after class                | Always `__init__()`             |
| Type declarations | Required (e.g. `String name`)    | Not required (dynamic typing)   |
| Access modifiers  | `public`, `private`, `protected` | No enforced access control      |

Initially, I was confused because I didn’t understand why Python needed self, unlike Java where the compiler manages access via this. After practicing, I now see how Python emphasizes explicitness, which improves readability.

---
## Goals for Tomorrow
- Practice building more Python classes with methods and attributes
- Study file I/O and exception handling in Python
- Start studying basic AI

