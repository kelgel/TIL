# 2025-07-17 TIL Clarification Prompt Strategy

## What I did today
- Explored how to handle ambiguous emotional expressions in user queries during prompt design.
- Studied when and how to insert a Clarification Prompt step in the LangChain-based AI book recommendation chatbot.

---

## What I learned
- ### 🧠 Clarification Prompt Strategy (Emotion-Based Recommendation System)
Added a new prompt step to handle vague or ambiguous emotional inputs:

- Clarification Prompt
  
  → Ask follow-up questions when the user's intent or emotional state is unclear (e.g., "슬픈 책 추천해줘"). which means recommend sad books.   
  → Encourage users to clarify their needs while gently guiding them toward the service's emotional recommendation purpose.

- Clarification Prompt Design Goals

  Identify if the query expresses a clear emotional need   
  If ambiguous, generate a clarifying question   
  If clear, proceed to refinement and recommendation   


| Step | Stage Name            | Description                                       |
| ---- | --------------------- | ------------------------------------------------- |
| 1    | Query Analysis        | Extract keywords, intent, constraints             |
| 2    | Intent Classification | Identify if it's a recommendation or info request |
| 3    | Clarification Prompt  | Clarify vague emotional intent                    |
| 4    | Query Refinement      | Convert to SQL or vector-ready form               |
| 5    | Filter Construction   | Prepare vector/DB filtering                       |
| 6    | Answer Generation     | Generate user-facing response                     |


- 🧠 Emotion Keyword Strategy
  
| Approach  | Pre-tag Emotion in DB                                     | Real-time Emotion Analysis              |
| --------- | --------------------------------------------------------- | --------------------------------------- |
| Timing    | During book ingestion                                     | At time of user query                   |
| Pros      | Fast, consistent, supports filtering                      | Dynamic, adapts to user’s current state |
| Cons      | Depends on pre-tag accuracy                               | Slower, more complex                    |

- Hybrid Strategy

Save emotion keywords during preprocessing → use in vector DB metadata   
Analyze user input at runtime → combine with embedding filters
→ Enables both emotional and contextual matching

---

## Reflections
- Designing a Clarification Prompt step helped me understand how to manage ambiguous user input more effectively.
- It also clarified that chatbot interaction is not just answering — it’s also guiding users toward meaningful interaction.

---

## Goals for Tomorrow
- Implement the Clarification Prompt step as a LangChain PromptTemplate.
- Start designing the metadata schema for emotion + tone tagging in vector DB.

