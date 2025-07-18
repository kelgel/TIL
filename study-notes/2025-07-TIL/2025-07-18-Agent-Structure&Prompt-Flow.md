# 2025-07-18 TIL – Agent Structure & Prompt Flow

## What I did today
- Compared MainAgent + Tools vs. multi-Agent architecture
- Reviewed how each prompt step (query analysis, clarification, etc.) is used in the system
- Learned about LLM response competition and when it should be applied

---

## What I learned

- ### 🧱 Agent Strategy
Starting with a single MainAgent + multiple Tools is simpler and faster for MVP development.   
We can later replace Tools with modular Agents without changing the overall flow.   

- ### 🔍 Prompt Step Execution
Prompt steps like query analysis, speech act classification, and clarification happen before calling the MainAgent.   
If input is vague (e.g. "fun book"), a clarification prompt is triggered and the flow restarts after user input.

- ### 🏆 LLM Response Competition (Requirement from  project)
In the final answer generation step, call the LLM multiple times.   
Compare results using scoring logic (e.g. keyword match, relevance).   
Return the best answer or summarize multiple outputs.  

---

## Reflections
- Building with a MainAgent + Tools first makes debugging and development much easier. 
- LLM response competition is a powerful but optional enhancement for final output quality.

---

## Goals for Tomorrow
- Keep studying on LnagChain components and methods

