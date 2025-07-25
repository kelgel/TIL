# 2025-07-25 TIL-From Prompt-based Agent to Vector-Powered Recommendation
## What I Did Today
- Reviewed the current implementation status of our chatbot system and outlined the next steps.
- Completed the initial version of recommend_agent using prompt-based recommendation logic — the agent can now generate basic book suggestions.
- Merged individual agent files and successfully connected the Python chatbot backend to the Java bookstore project via API.

---

## What I Learned
- ### 🧠 Handling Conversation Flow and Edge Cases
  Even after clarification (e.g., user fills in missing emotion), the query must be re-analyzed, as the user's intent might change.
  Mapping out exception flows (e.g., missing genre, ambiguous author names) in advance is critical for building a robust system.

- ### 📡 Preparing for Vector DB Integration
  Before connecting to Chroma, it's important to clearly define:
    - What input format to send for retrieval
    - What metadata to embed (emotion + genre + description, etc.)
  Recommendations can start with prompt-only, then evolve into semantic search-powered results.

- ### 🚧 Current Implementation Status & Next Steps
  | Phase                            | Goal                                               | Key Technology                             | Status                       |
  | -------------------------------- | -------------------------------------------------- | ------------------------------------------ | ---------------------------- |
  | 1️⃣ Intent-based Response Flow   | Implement intent classification and query routing  | Intent classification chain, agent routing | ✅ In progress                |
  | 2️⃣ Individual Agent Development | Build agents like `recommend_agent`, `order_agent` | LangChain + prompt + tools                 | 🛠 Working on RecommendAgent |
  | 3️⃣ Memory Support               | Maintain context across turns                      | `ConversationBufferMemory`, chat history   | 🔜 Next                      |
  | 4️⃣ Personalized Recommendation  | Recommend books based on user preferences          | Logs, user profiles, filtering             | ⏳ Future plan                |

---

## Reflections
- It was helpful to take a step back and assess what’s implemented and what still needs work.
- Realized the importance of starting from simple prompt-based logic, then gradually incorporating vector search (Chroma) for more intelligent recommendations.
- Integrating the Python service with the existing Java backend early helped ensure the overall flow is working before diving deeper into AI logic.

---

## Goals for Tomorrow
- Connect recommend_agent with Chroma vector DB and test real retrieval-based book suggestions.
- Begin designing how memory (e.g., ConversationBufferMemory) can be added for smoother multi-turn conversations.

