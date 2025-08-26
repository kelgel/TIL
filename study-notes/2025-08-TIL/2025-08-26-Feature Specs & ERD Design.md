# 2025-08-26 TIL — Feature Specs & ERD Design

## What I did today

- Updated feature specs for Scheduler, Product Crawling, LLM Content Generation, and Publishing.
- Designed the MVP ERD including product, generation_job, content, prompt_template, model_config, trend_keyword etc.

---

## What I learned

- Use normalized schema (product + product_detail) for scalability but simplify for MVP.
- Nginx helps centralize routing and avoid CORS issues. (But stil needs the research about it.)

---

## Reflection
- Separating product snapshots from normalized details is only necessary in later stages for debugging, audits, and LLM improvements.
  For MVP, simpler schemas and fewer tables will help us iterate faster without blocking on DB modeling.

---

## Goals for Tomorrow

- Finalize the LLM API request/response spec.
- Complete the MVP ERD diagram.
- Prepare initial API documentation for both backends.
