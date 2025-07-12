# 2025-07-12 TIL Java 05 &Entity Manager

## What I did today
- Reviewed java Chapter 5 : Arrays
- Studied EntityManager and EntityTransaction in Spring Boot / JPA 

---

## What I learned
- ### 🔹 Java – Arrays (Chapter 5)   
  `Arrays are containers that hold multiple values of the same type.`  
  - Arrays have fixed size once initialized.  Can be initialized directly: String[] names = {"Alice", "Bob"}.
  - Arrays are reference types in Java, not primitives.    
  📌 Key Concepts:   
  - Array memory is allocated on the heap.
  - Array variables store references, not the actual values.


- ### 🔹 Spring Boot – EntityManager & EntityTransaction
  🧩 EntityManager
    - Central interface in JPA for interacting with the persistence context.
    - Handles CRUD operations, queries, transaction control, and entity lifecycle.
  
  ⚙️ EntityTransaction
  - Used to manually control transactions (when not using Spring @Transactional).
  - Spring Boot typically abstracts this using @Transactional.
  
  🧠 Persistence Context
    - The first-level cache where managed entities are tracked.
    - All changes to entities are synced to the DB at commit time.
    - Prevents duplicate SQL by reusing loaded entities in the same transaction.

---

## Reflections
- Arrays seem simple at first, but understanding how they work in memory and interact with reference types is important for avoiding bugs.
- Understanding manual transaction boundaries gave me a more concrete picture of what @Transactional actually does behind the scenes.

---

## Goals for Tomorrow

- Practice writing JPA queries using EntityManager
- Study Java methods and parameters (Chapter 6) for tomorrow’s review session.
  
