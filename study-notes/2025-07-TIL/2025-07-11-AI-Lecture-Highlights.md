# 2025-07-11 TIL AI special lecture

## What I did today
-  Reviewed core Java concepts, especially how a basic Java program is structured.
- Attended a special lecture on AI systems.

---

## What I learned
- ### 🔹 New Perspective of Hello World in Java Structure
Java programs consist of: package declaration → import (e.g. java.lang) → class declaration → fields and methods.
  - public: can be called from outside the class.
  - static: allows access without creating an object (static = class-level).
  - void: return type when no value is returned.
  - main: the entry point; JVM searches for this method to start execution.
  - String[] args: used to receive runtime arguments.
  - System: part of java.lang package.
  - out: a public static member of System class.
  - println: method invoked on out, takes arguments (usually strings), prints them.

➡️ Concepts like polymorphism, abstraction, and encapsulation are all present — important to identify and understand them clearly.

- ### 🔹 RDBMS & JPA Basics
RDBMS = Relational Database Management System.
- PK (Primary Key): uniquely identifies each row, must be unique.   
- UK (Unique Key): similar to PK but not necessarily primary.    
- FK (Foreign Key): links to PK/UK of another table.
- Index: speeds up query (especially SELECT) and prevents full table scan.

(+) JOIN Strategy:
Reduce large sets using smaller tables in outer queries.
Use LEFT JOIN to include unmatched rows from the left.
SELECT = set operation; FROM, WHERE, JOIN form intersections, unions, or complements.

- ### 🤖 AI Lecture Highlights
🔹 Transformers
Introduced with Google's Attention mechanism in “Attention Is All You Need”.
Can handle unstructured/abstract data → enables training with much larger datasets.
Compresses long sentences via attention mechanism.
Brought scalability to new levels.

🔹 Scaling Laws
Even if accuracy drops slightly, scaling works:
  More training data
  More input data
  More model parameters
→ All improve performance.

🔹 AI as a Tool for Tools
Agent: autonomous system acting to achieve a goal.   
MCP (Model Context Protocol): internal communication format between components of a model.  
A2A (Agent-to-Agent): external communication between different agents.

🔹 Gemini & RAG
Google Gemini performs RAG (Retrieval-Augmented Generation) via search integration.
Training-Time Scaling has limits (data, compute).

Enter Inference-Time Scaling:
Improve performance not by more data, but by smarter reasoning during inference.
Extract deeper knowledge from existing parameters.
More efficient → requires less hardware, but longer inference time.

---

- ## Reflections
Explaining concepts to others is the true test of understanding — I need to practice this more.
The AI session helped me connect academic theory (e.g., scaling laws) with practical tools like Gemini.
Database strategies such as indexing and JOIN optimization gave me a new perspective on SQL performance.

---

- ## Goals for Tomorrow
- Apply EXPLAIN in SQL queries on my bookstore project to check performance.
