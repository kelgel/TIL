# 2025-07-14 TIL RAG Concept

## What I did today
- Reviewed Java Chapter 6: class structures, focusing on class declarations, fields, methods, and access modifiers.
- Participated in the first team project meeting: discussed direction, shared service ideas, and aligned on project goals.
- Studied Retrieval-Augmented Generation (RAG) architecture and its 8-step pipeline.

---

 ## What I learned
- ### 🟦 Java – Class Review
  A class is a template for creating objects, encapsulating data (fields) and behavior (methods).
  
  Access Modifiers:
    public: accessible from anywhere.
    
    private: accessible only within the class.
    
    protected: accessible within the same package or subclasses.

  Constructor: a special method used to initialize objects.

  Static: belongs to the class, not to instances.
 
  📌 Key Concepts:    
  Separation of data (fields) and actions (methods) improves maintainability.
  
  Java enforces encapsulation via access control.

- ### 🤖 RAG – Retrieval Augmented Generation
  A framework that combines retrieval and generation to overcome the limitations of standalone language models.    

  ### 🔧 Preprocessing Steps
    Document Loader
    → Loads and pre-processes external documents from various sources.
    
    Text Splitter
    → Splits large texts into smaller, manageable chunks.
    
    Embedding
    → Converts each chunk into a numerical vector that captures its semantic meaning.
    
    Vector Store
    → Stores embedded vectors in a vector database for fast similarity-based retrieval.
  
  ### 🚀 Runtime Steps
    Retriever
    → Retrieves the most relevant vectors from the vector DB based on the input query.
    
    Prompt Constructor
    → Builds a prompt for the LLM using the retrieved context chunks.
    
    LLM (Language Model)
    → Generates a response based on the constructed prompt.
    
    Chain
    → Combines all steps into a cohesive pipeline for seamless execution.

---

## Reflections
- Reviewing Java classes reminded me of how essential structure and visibility are in object-oriented design.
- RAG’s clear pipeline was fascinating. Each component (Loader, Embedder, Retriever...) serves a purpose that maps perfectly to real-world search & generation.

---

## Goals for Tomorrow
- Write example code using TextSplitter and VectorStore with LangChain.
- Study Java (Chapter 7) for tomorrow’s review session.
