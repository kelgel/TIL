# 2025-07-22 TIL – Python Module Execution & Chain Flow Debugging

## What I did today
- Learned the difference between running Python files as scripts vs. modules (python file.py vs. python -m module)
- Fixed an import error by understanding Python’s module resolution behavior
- Identified and debugged a logic bug in the intent classification prompt
- Studied how RunnableLambda can be used to process LLM output inside LangChain chains

---

## What I learned

- ### 🐍 Python Module Execution
  - Running `python main_agent/main_agent.py` treats the file as a script → relative imports fail   
  - Running `python -m main_agent.main_agent` treats it as a module → imports work from project root


- ### 📦 __init__.py Purpose
  - Marks directories as Python packages  
  - Prevents import errors across folders  
  - Best practice: include it in all functional subfolders (main_agent, tools, prompts, etc.)

- ### 🧠 Prompt Flow Debugging
  - Discovered a mistake where the intent classification prompt was fed a JSON output, not the original user input
  -> Fix: always pass the raw user input to intent classification, not intermediate structured results

- ### 🛠 LangChain – RunnableLambda vs Tool
  | Component        | Role                                                 | Used in            |
  | ---------------- | ---------------------------------------------------- | ------------------ |
  | `Tool`           | External action (DB, API, search)                    | Agent actions      |
  | `RunnableLambda` | Inline Python function for transforming chain output | Used inside chains |
  
  - Used to convert LLM JSON-like text to a usable Python dict

---

## Reflections   
- It’s easy to break chain logic if inputs are misaligned — prompt input/output format must be exact
- The more I write code, the more I realize there’s so much to learn — but it’s really interesting!
  
---

## Goals for Tomorrow
- Modularize prompt + LLM + parsing components in chains/
- Start testing RecommendAgent flow end-to-end with multiple user inputs
