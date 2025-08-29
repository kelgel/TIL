# 2025-08-29 TIL – Wiring FastAPI for LLM and Preparing Spring ↔ FastAPI Bridge

## What I did today

- Created ai-service/ and a Python venv; installed fastapi, uvicorn, pydantic.
- Implemented app.py with two endpoints: GET /health, POST /v1/generate/post (mock response).
- Opened a new branch feature/ai for all AI-related work.

---

## What I learned

- FastAPI basics: FastAPI() app, route decorators (@app.get, @app.post), and response_model for auto-validation/serialization.
    Pydantic models with type hints (List[str], Optional[str]) to validate request/response bodies.
- Worked on reviewing basic python grammars about LangChain + LLM.

---

## Reflections

- Starting with a tiny E2E (mock generation) removed uncertainty and makes Spring integration straightforward.
- Locking a provisional schema early (even if small) helps the team move in parallel.

--- 

## Goals for Tomorrow

- From Spring Boot, call POST /v1/generate/post using WebClient (add DTOs, LlmService, and a test controller).
- Save the returned PostDraft into posts table (status=READY).
- Convert mock to real LLM call (OpenAI/Gemini) behind the same endpoint and add simple guardrails (banned words, length check).
