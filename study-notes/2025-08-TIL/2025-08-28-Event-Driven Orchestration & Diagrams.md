# 2025-08-28 TIL — Event-Driven Orchestration & Diagrams

## What I did today

- Drew sequence diagrams for admin/scheduler flows and added data lifespan span
- Take a role as the part of the llm fields

---

## What I learned

- Mixing sequence + shaded spans clearly shows data lifecycles.

- Event-driven orchestration (Producer → Orchestrator → Consumer) decouples LLM calls, enables async, and scales:

    e.g., PRODUCT_READY → orchestrator → FastAPI(LLM+guardrails) → save posts(READY) → emit POST_READY.

---

## Reflections

- It takes time to draw and fix the diagrams but definitely helps to understand the flow of the project.

---

## Goals for tomorrow

- Analyize the RFP and project more to keep working on ERD.
- Work on concept of the orchestration and llm (prompts) before programming.
