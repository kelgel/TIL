# 2025-07-16 TIL Prompt Structuring

## What I did today
- Studied prompt structuring strategies before implementing the LangChain chatbot.
- Analyzed the data retrieval flow for building an emotion-based AI book recommendation chatbot for the bookstore team project.

---

## What I learned
- ### 🧠 Prompt Structuring (LangChain + RAG)
  
  `Designed a multi-step prompt pipeline for book recommendation:`
  
  - Query Analysis: Extract emotion, genre, and keywords.
  
  - Intent Classification: Detect whether it’s a recommendation, comparison, or info request.
  
  - Query Refinement: Clarify vague questions via LLM or follow-up prompts.
  
  - Filter Generation (NL2SQL): Convert user intent into database filter/query.
  
  - Answer Generation: Create empathetic, natural language responses.
  
  `Mixed strategy for vague input:`
  If emotion + genre are clear → proceed with recommendation.
  If missing → ask clarifying questions via prompt.
  
  `Few-shot prompting improves accuracy and structure consistency:`
  Embedded examples help guide LLM output.
  PromptTemplate in LangChain allows flexible example injection (static or dynamic).

---

## Reflections
- Defining each prompt step before implementation gives me a clear structure to follow but still needs to practice more.
- RAG isn’t just about retrieval — it’s about orchestrating smart generation through structured inputs.

---

## Goals for Tomorrow

- Implement the first version of the query analysis prompt using LangChain's PromptTemplate.
- Start defining the vector DB schema for storing book embeddings.
- Draft test cases for edge prompts (e.g., no emotion, multi-intent queries).
