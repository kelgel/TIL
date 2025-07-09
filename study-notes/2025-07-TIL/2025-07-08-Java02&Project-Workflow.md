# 2025-07-08 TIL — Java Chapter 2 & Project Workflow & Review Spring Boot

## What I Did Today
- Learned the real-world software development process including problem definition, requirement analysis, design, coding, and testing.
- Reviewed Spring Boot backend concepts, especially around how HTTP request/response work internally.
- Continued studying Java Chapter 2: Variables and Data Types, with practical examples and quiz-style review questions.

---

## What I Learned
- ### 🛠 Software Development Lifecycle
  A real-world project involves far more than just writing code:    
  `📍 Problem Definition → 🧠 Requirements Analysis → 🏗️ System Design → 💻 Coding → ✅ Testing & QA`    
  It was eye-opening to realize how many non-coding steps are essential for building scalable and maintainable software.  
  Communication, documentation, and architecture decisions matter just as much as syntax.

- ### 🌐 Spring Boot & Web Basics
  - WAS (Web Application Server): Provides application services via HTTP (e.g., Tomcat).
    Allows client programs to remotely execute server-side applications.

  - HttpServletRequest & HttpServletResponse:
    Enable communication between client and server.

  - getParameter() and getParameterValues() are used to extract query data.
  
  - Content-Type & MIME: Defines how data is encoded in HTTP (e.g., application/json, text/html).
  
  - URL Rewriting: Technique to pass parameters via query strings for session tracking or dynamic behavior.

- ### ☕ Java Chapter 2: Variables & Data Types
  Java provides primitive types (8 total):   
  | Category  | Types                          |
  | --------- | ------------------------------ |
  | Integer   | `byte`, `short`, `int`, `long` |
  | Float     | `float`, `double`              |
  | Character | `char`                         |
  | Boolean   | `boolean`                      |

  - Type Casting:
    Implicit: int → long (safe widening)
    Explicit: double → int (needs cast and truncates)

  - Constants: Declared with final, cannot be reassigned.
    
- ### ✅ Review Questions for Java
  Q1. List Java's 8 primitive types
  
  `byte, short, int, long, float, double, char, boolean`
  
  Q2. Is float f = 3.14; valid?
  
  `❌ No, 3.14 is double by default. Use 3.14f or (float)3.14.`
  
  Q3. What is the result of int i = (int)3.99;?
  
  `3 — decimal is truncated, not rounded.`
  
  Q4. Meaning of final int LIMIT = 100;
  
  `Declares an immutable constant. Value cannot be changed after assignment.`

---

- ## Reflection
  I was surprised at how complex real-world software development is — writing code(programming) is just one piece of the puzzle.   
  Reviewing WAS and HTTP helped me better understand how Spring Boot handles client-server interaction.    
  Revisiting Java syntax and type system made me more comfortable with core principles like constants, casting, and data types.

---

## Goals for Tomorrow

- Continue CSS and building CRUD features for the admin book panel in Spring Boot.
- Study Java Chapter 3: Operators and Expressions.
