# Weekly TIL: 2025-07-07 ~ 2025-07-13

## ✅ Highlights of the Week
- Completed Java Chapters 4–5: Loops and Arrays.
- Studied Spring Boot JPA internals: EntityManager, EntityTransaction, and persistence context.
- Attended a seminar on AI architecture, focusing on inference-time scaling and Google's Gemini RAG model.
- Decided to write a weekly til on every Sunday.

---

## 📚 What I Learned
- ### 💡 Java
  - Loops
  Studied the use of for, while, and do-while loops.
  Understood differences between pre- and post-increment operators.
  
  - Arrays
  Arrays are reference types stored on the heap.   
  Can be iterated with for-each, but this does not allow index access.   
  `.length` is a property, not a method.   
  Multi-dimensional arrays and memory structure reviewed.   

- ### ⚙️ Spring Boot / JPA
  - EntityManager provides low-level access to the persistence context.   
  - EntityTransaction is used for manual transaction handling (outside Spring).   
  - Spring’s @Transactional abstracts the boilerplate of EntityTransaction.   
  - The persistence context manages entity states, reduces duplicate SQL via first-level cache.   

- ### 🧠 AI / Systems
  - Transformers introduced by "Attention is All You Need" — enabled unstructured data learning.  
  - Scaling Laws : More data, training, and parameters → better model performance.  
  - Inference-Time Scaling : Boosts performance by reasoning more during inference instead of just increasing training scale.
  - Google Gemini uses RAG (Retrieval-Augmented Generation) to pull information via live search for generation tasks.

---

## 🔍 Things I Struggled With
- Grasping the full lifecycle of JPA-managed entities.
- Knowing when to use EntityManager manually vs. relying on @Transactional.
- Finding a right way to Spring Boot - still struggling.

## 🧠 Insights / Reflections
- Writing TILs and rephrasing what I learned is helping me retain concepts better.
- Learning the lower-level mechanics (JPA, transactions) gave me more control and understanding.
- AI system design is shifting from scale everything to reason smarter — a direction worth following.

## 🎯 Goals for Next Week
✅ Study Java Chapter 6-10  
✅ Create a basic CRUD feature using Spring Boot and JPA manually. - keep working on the assignment    
✅ Implement a simple RAG example using LangChain.  
