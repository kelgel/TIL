# 2025-08-25 TIL — Feature Specs for AI Content Automation

## What I did today

- Wrote a reusable Function Spec template (purpose, inputs, process, outputs, errors, test cases).
  - LLM Content Generation, Product Crawling, Publish and then simplified to an MVP
- Worked on the user flow

---

## What I learned

- How to draw a user flow from the perspective of the user and the system (Scheduler)
- Specs should be QA-ready: define Inputs → Process → Outputs → Exceptions → Test cases.
- Async decoupling boosts resilience/scale but adds ops cost; start synchronous for MVP.
- Use Strategy adapters for parsers; only use Playwright when JS rendering is required.

---

## Reflections

- The MVP path reduces risk and shows value quickly; we can layer queues/scheduling later.
- Working on the user flow, it was able to notice or add additional functions for the program.

---

## Goals for tomorrow

- Prepare for second meeting with the company.
- Research more about a basic crawler for one source (Jsoup)
- Keep working on feature specs - Results/Logs spec and a minimal admin view for publish status.
