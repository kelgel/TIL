# 2025-07-02 Python Syntax Practice & ML/DL Concept Review

## What I Did Today

- Reviewed and practiced Python basics: conditionals, loops, functions, classes, file I/O, and more
- Solved exercises using lambda, map, filter, list comprehension, and variable arguments
- Learned the key difference between **machine learning** and **deep learning**

---

## What I Learned

- ### Python Syntax & Functional Tools

- **Lambda Functions**: Anonymous functions used for quick operations in `map`, `filter`, etc.
- **`map()` vs List Comprehension**:  
  Both can be used to transform lists, but `map()` returns a lazy object and must be converted to `list()` for display.
  ```python
  doubled = list(map(lambda x: x * 2, [1, 2, 3]))
  doubled = [x * 2 for x in [1, 2, 3]]
  ```
- Variable Arguments:
  ```python
  def add_many(*args):  # args as tuple
  def print_kwargs(**kwargs):  # kwargs as dictionary
  ```
- Tuple Unpacking in Returns:
  ```python
  def add_and_mul(a, b):
    return a + b, a * b
  sum_val, product = add_and_mul(3, 4)  # (7, 12)
  ```

- map() in Python vs map() in Java Streams
  While I was studying map() in Python, I found something similar to map() in Java Streams, so i just compared in simply way:
  
| Feature         | Python `map()`              | Java Stream `.map()`                          |
| --------------- | --------------------------- | --------------------------------------------- |
| Lazy Evaluation | ✅ Yes                       | ✅ Yes                                         |
| Chaining        | ❌ Limited                   | ✅ Full chaining (`.map().filter().collect()`) |
| Result          | `map` object (one-time use) | Stream object (also one-time use)             |


- ### Machine Learning vs Deep Learning
  I learned that the main difference between machine learning and deep learning is who performs feature extraction:
  In machine learning, human experts manually extract and select features.
  In deep learning, the model learns to extract features automatically from raw data.

---

## Goals for Tomorrow

- Practice object-oriented programming with class-based problems
- Review scikit-learn basics to prepare for machine learning hands-on exercises




