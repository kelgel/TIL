# Weekly TIL: 2025-07-14 ~ 2025-07-20

## ✅ Highlights of the Week
- Finalized the architecture for emotion-based AI book recommendation chatbot using LangChain + RAG.  
- Designed prompt workflows with multi-stage templates (intent, act type, clarification, etc).  
- Implemented pipeline: extract emotion keywords from book descriptions → save to MySQL → embed to Chroma vector DB.
  
  (Weekly blog : https://velog.io/@gkeuni/커널아카데미-백엔드-부트캠프-17주차-토이프로젝트4-1-회고 )

---

## 📚 What I Learned

- ### 💡 LangChain / Prompt Engineering
  - Designed prompt flows in 5+ stages: query analysis → speech act classification → clarification → NL2SQL → answer generation.  
  - Learned when and how clarification prompts are triggered, and how they short-circuit the main agent.  
  - Few-shot prompting improves structure and consistency of responses.

- ### 🧠 RAG + Vector DB
  - Stored extracted emotion keywords in MySQL for structured filtering.
  - Combined emotion + description → embedded into Chroma vector store for retrieval.
  - Understood how metadata filtering works during vector search.
  - Clarified difference between when to use structured DB vs vector DB.

- ### 🛠️ Tooling / System Design
  - Explored design tradeoffs: 1 Main Agent vs. Multi-Agent system.
  - Studied how to log and store intermediate LLM outputs (user input, parsed intent, clarified input, etc).

---

## 🔍 Things I Struggled With
  - Choosing which books to embed if emotion keywords are missing — decided to store all and filter later.
  - Managing both Spring Boot and LangChain pipelines in one service—need better separation.
  - Unsure where to insert LLM reranking (LLM competition step) within RAG flow.
  - How to decide and set up which agents and tools to use

---

## 🧠 Insights / Reflections
  - Clarifying each prompt stage early prevents confusion during implementation.
  - Combining structured + semantic filtering gives more powerful recommendation logic.

---

## 🎯 Goals for Next Week (07.21 ~ 07.27)
- ✅ Containerize the full pipeline with Docker (MySQL + FastAPI + Chroma).
- ✅ Build contract upload + summarization MVP in Spring Boot.

