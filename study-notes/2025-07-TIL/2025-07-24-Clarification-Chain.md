# 2025-07-24 TIL – Clarification Chain, Intent Routing & AIMessage Handling in LangChain

## What I did today
- Implemented get_clarification_prompt(intent) to return appropriate prompt based on user intent.
- Faced a common issue: AIMessage object vs. str when handling LLM responses.
- Fixed AttributeError: 'dict' object has no attribute 'content' by parsing .content properly.
- Handled repeated clarification attempts and logic for when emotion/genre is still missing.

---

## What I learned
- ### 🧠 Clarification Chain Design
Clarification chains must be modular since prompts vary by intent (recommendation, info, order_check, etc.).
Intent like "clarification" itself should not enter the clarification flow; skip this to prevent prompt mismatch.

- ### 🧽 Parsing AIMessage safely
LLMChain returns AIMessage, not raw string.
To parse JSON reliably:
```
if hasattr(output, "content"):
    output = output.content
return json.loads(output)
```

- ### 🐛 Debugging Tips
When .content is missing, accessing fields like clarification_message.content leads to runtime errors.
Always ensure the output is a string before applying .strip(), .lower(), or json.loads().

---

## Reflections
- Modular chains help manage intent-specific prompts and avoid hardcoded logic in the main agent.
- Handling user responses across multiple rounds requires a loop or state memory—I'll consider integrating this later.
- LangChain's newer Runnable syntax is powerful but needs careful output processing.

---

## Goals for Tomorrow
- Add fallback responses when clarification fails repeatedly.
- Handle mutiple questions at once in main agent
