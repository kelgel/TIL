# 2025-08-27 TIL - Singleton&Keeping the AI Content Pipeline Simple

## What I Did Today

- Finalized a feature-sliced backend structure (trend → crawl → content → publish).
- Drew and fixed Mermaid diagrams (use case, sequence).
- Studied for the Singleton desgin pattern with the access modifier of constructor.

---

## What I Learned

- Sequence vs Use-case: sequence = order/time; use-case = actors/scope.

- Normalization: 3NF for operational tables; snapshots/logs can be denormalized.

- AOP logging is optional; WebClient summary + MDC covers most cases.

- Singleton (Java):

  Private constructor blocks external instantiation; class controls creation.
  
  Hold a static instance and expose public static getInstance().
  
  All callers get the same object (saves memory for heavy resources).

---
  
## Reflections

- Minimal guardrails (errors, logging, tiny tests) keep speed with safety.
- Interesting to learn singleton design pattern in the perspective of the constructor.

---

## Goals for Tomorrow

- Modify and finalize diagrams (use case, sequence).


