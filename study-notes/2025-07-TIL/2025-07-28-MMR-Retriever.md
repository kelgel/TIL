# 2025-07-28 TIL – Enhancing Book Recommendations with MMR Retriever in LangChain

## What I did today
- Refactored the run_recommend_agent function to use a retriever created via as_retriever(search_type="mmr") instead of manually using similarity_search.
- Encountered an issue with the vector database, so I reprocessed the embeddings.
- To save time, I reused a previously compressed and stored file containing the same embedding data.

---

## What I learned

- ### 📚 MMR vs. Standard Similarity Search
| Aspect                     | Similarity Search          | MMR Search (`search_type="mmr"`)            |
| -------------------------- | -------------------------- | ------------------------------------------- |
| Selection Strategy         | Top-k by cosine similarity | Balances similarity & diversity             |
| Output Order               | Most similar first         | Starts with most similar, then adds diverse |
| Risk of Repetitive Results | High                       | Low                                         |
| Ideal For                  | Exact match needs          | Recommendation systems (like books)         |

- MMR (Maximal Marginal Relevance) improves recommendation quality by reducing redundancy and increasing diversity in search results.
- The as_retriever() approach makes the system modular and easier to plug into LangChain tools, agents, or memory-enhanced pipelines.

---

## Reflection
- Switching to MMR and using retriever-based retrieval cleaned up the code and enhanced future scalability. 
- Today’s vector DB issue reminded me of the importance of managing persistent storage wisely. 

---

## Goals for Tomorrow
- Refactor and modularize it (e.g., separating prompt, retriever, chain, and logic - The current recommendation agent logic is all written in a single file).
- Integrating memory to make the chatbot stateful and capable of maintaining conversational context.

