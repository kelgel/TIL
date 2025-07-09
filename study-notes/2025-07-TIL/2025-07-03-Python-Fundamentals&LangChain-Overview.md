# 2025-07-03 TIL – Python Fundamentals & LangChain Overview

## What I Did Today

- Reviewed basic Python syntax and data structures through the exam
- Studied Python’s object model, including identity, mutability, and variable binding
- Learned about shallow vs deep copy in Python
- Explored LangChain: structure, installation, and simple usage

---

## What I Learned

- ### Python's Call by Object Reference (a.k.a. Call by Sharing)
- Python passes **references to objects**, not the actual objects themselves.
- If the object is **immutable** (`int`, `str`, `tuple`), modifying it inside a function creates a new object.
- If the object is **mutable** (`list`, `dict`, `set`), in-place modifications **affect the original** object.

#### Example 1: Immutable Type (`int`)
```python
def change_value(x):
    x += 10

a = 5
change_value(a)
print(a)  # Output: 5 (unchanged)
```
#### Example 2: Mutable Type (`list`)
```python
def append_item(lst):
    lst.append(100)

nums = [1, 2, 3]
append_item(nums)
print(nums)  # Output: [1, 2, 3, 100]
```

- ### Shallow Copy vs Deep Copy in Python   
| Type         | Description                                                        |
| ------------ | ------------------------------------------------------------------ |
| Shallow Copy | Copies the outer container; references the **same** inner objects. |
| Deep Copy    | Recursively copies all nested elements into **new objects**.       |

---

- ### LangChain Introduction
LangChain is an open-source Python framework for building LLM (Large Language Model) powered applications.  
It helps chain together prompts, LLMs, tools, memory, and retrievers.     

  - Core Components:

| Component        | Description                                  |
| ---------------- | -------------------------------------------- |
| `LLM`            | Language model (e.g., OpenAI GPT)            |
| `PromptTemplate` | Template for dynamic prompt creation         |
| `LLMChain`       | Chains prompt with LLM for single-step tasks |
| `Memory`         | Stores previous messages (optional)          |
| `Retriever`      | Finds and returns relevant documents         |  

  - Example Flow: `User Input → PromptTemplate → LLMChain → Result`
  - 1️⃣ What is a PromptTemplate?   
      A PromptTemplate is a tool used to create reusable prompt structures where specific parts can be dynamically filled in with user input or variables.
  
  - 2️⃣ What is an LLMChain?   
      An LLMChain connects a PromptTemplate with a language model (LLM) to form a complete input-to-output processing flow within LangChain.
    
---
## Goals for Tomorrow

- Continue solving Python exercises
- Explore LangChain memory & retrieval modules
