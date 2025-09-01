# 2025-09-01 TIL – FastAPI ↔ Spring Bridge with LangChain

## What I did today

- Set up ai-service/ (venv) and built GET /health, POST /v1/generate/post.
- Connected Spring Boot → FastAPI via WebClient with minimal DTOs.
- Swapped mock for LangChain (ChatOpenAI + PydanticOutputParser).
- Tested with Swagger/Postman; fixed a missing leading / in route.

---

## What I learned

- FastAPI + Pydantic make strict, self-documented JSON contracts easy.
- LangChain’s prompt → model → Pydantic parsing keeps outputs reliable.
- Keeping Spring DTOs snake_case avoids extra Jackson config.

---

## Reflections

- Start tiny: a mock E2E first, then swap in real LLM = faster, calmer progress.

---

## Goals for Tomorrow

- Save PostDraft to posts (status=READY) and add an admin run-once.
- Add a daily @Scheduled job (08:00 KST) for the pipeline.
