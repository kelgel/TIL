# 2025-08-21 TIL – Kickoff, RFP Analysis

## What I did today

- Analyzed RFP and translated into concrete scope:
- Channel decision: Naver Blog auto-post not available → searching for other way
- Set team rules: code convention & git strategy

---

## What I learned

-  ### Team rules 

  - Code conventions: Google Java Style; package by layer (controller/service/repository/config); RESTful paths; records for DTOs; parameterized logging; 
  - Git branching: short-lived branches feat/…, fix/…, chore/…; Conventional Commits; ≥1 reviewer; small PRs; squash merge; CI (build+tests) required.

---

## Reflections

-  The RFP constraints keep scope tight; MVP stays simple while leaving room for RAG (Lite→Full) and an “improve-until-score” loop later.

---

## Goals for tomorrow

- Implement DraftChain (LangChain4j) → HTML Renderer → SeoValidator; persist DRAFT with manual override.
- Meeting with company
