# 2025-07-23 TIL – Lastest Syntax - Modular Chain Design & LLM Output Handling in LangChain

## What I did today
- Migrated query_analysis_chain into its own file for potential reuse across multiple agents
- Learned to use the latest Runnable-based LangChain syntax with | pipe operator and invoke()
- Handled an error involving AIMessage object vs. raw string when parsing LLM output

---

## What I learned

- ### 📦 When to Modularize Chains
  
| Situation                        | Recommendation                          | Why                                |
| -------------------------------- | --------------------------------------- | ---------------------------------- |
| Chain is reused or may be reused | ✅ Put in `chains/` as a separate module | Easy to manage, cleaner main logic |
| Chain is only used once          | ⚠️ Inline OK, but limits future reuse   | Can be harder to maintain          |

📌 In our project, query_analysis_chain might be reused by both MainAgent and ClarifyAgent, so it belongs in the chains/ folder.

- ### 🧱 New-Style LangChain Chains
  
```
from langchain_core.runnables import RunnableLambda
from utils.parse_intent import parse_intent

intent_classify_chain = intent_classify_prompt | intent_classify_llm | RunnableLambda(parse_intent)
```
Cleanly separates:
PromptTemplate → LLM → Post-processing

.invoke({"user_input": ...}) is the new preferred execution style (over .run())

- ### 🧽 Output Parsing with parse_intent()
LLMs return raw text like " Recommendation\n" → must be cleaned for internal logic

```
def parse_intent(output: str) -> str:
    return output.strip().lower()
```

- ### 🐛 Error Debugging: json.loads() and AIMessage
LangChain returns AIMessage(content=...), not just str
Fix: unwrap .content before parsing

```
if hasattr(output, "content"):
    output = output.content
return json.loads(output)
```

---

## Reflections
- Small decisions like modularizing chain logic make long-term debugging and extension much easier
- Prompt → LLM → Postprocessing needs to be clearly defined and separated
- Noticed the imporatance of using latest syntax,, not the deprecated one

---

Goals for Tomorrow
- Draw flowchart of the whole chatbot system
- Link RecommendAgent with clean chain + parsing logic

