# Weekly TIL: 2025-07-21 ~ 2025-07-27

## Highlights of the Week

- Understood and implemented the modular LangChain architecture: Agent ↔ Chain (Prompt + Tool)
- Successfully completed the full pipeline: book description → emotion keyword extraction → MySQL → Chroma embedding
- Wrote and structured multi-step prompt templates for intent detection, clarification, recommendation, and emotional responses
- Integrated Docker Compose for running MySQL and FastAPI services for local testing

---

## What I Learned

- ### 🧠 LangChain Structure
  - Agent is the controller.
  - Chain = Prompt + LLM + Runnable (parsing or tools).
  - Tools = real-world actions (DB queries, vector search).
  - Prompt = system message template that orders frames LLM behavior.
  - Modular folders (agents/, tools/, chains/, prompt_templates/) make the project clean and extensible.

- ### 🔧 Prompt Engineering
  - The performance relies on the prompt a lot.
  - Each function (query analysis, clarification, recommendation) requires its own prompt and chain.
  - Clarification prompt is only triggered when required fields (like emotion, genre) are missing.
  - Partial prompts and few-shot examples improve response stability.

- ### 🐍 Python & Execution Model
  - Learned the difference between running files as scripts vs. modules (python script.py vs. python -m module)
  - Fixed IntelliJ config to run LangChain modules correctly
  - Understood the importance of __init__.py in recognizing folders as packages

- ### 🐳 DevOps & Infrastructure
  - Successfully set up Docker Compose to launch MySQL + FastAPI together
  - This setup will support team development and deployment for the AI chatbot backend

---

## ⚠️ Challenges Faced
  - Misused JSON output from query analysis in intent classification → caused wrong predictions
  - json.loads() failed due to receiving AIMessage instead of str → fixed by extracting .content
  - Took time to grasp when to modularize chains and when to inline them
  - Programming takes longer than I expected - quite lots of exceptional situations

## 🧠 Reflections
- Separating prompt logic, tools, and chains pays off quickly as complexity grows
- Writing clarification prompts helped me better understand what makes a query ambiguous
- Try to study more concepts using official documents rather asking and using AI right away

---

## Goals for Next Week (07.28 ~ 08.03)
- Build and test the ClarifyAgent end-to-end with memory support
- Connect the main agent with other agents
- Begin writing unit tests for agents and chains 
- (+) Add logging and basic session tracking to support personalized recommendations
