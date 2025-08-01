# 2025-07-31 TIL – Fixing Incorrect Hybrid Tool Activation Logic

## What I Did Today

- Investigated a bug where the `hybrid_tool` was being triggered even when only one condition (e.g., genre) was present.
- Analyzed the `run_recommend_agent()` logic and found that `keywords` were being mistakenly included in the multi-condition check.
- Refactored the condition to only count `emotion`, `genre`, and `author` for hybrid recommendation activation.
- Verified that `genre_tool`, `author_tool`, and `emotion_tool` are now called correctly in single-condition cases.

---

##  What I Learned

- Not all extracted query parts should be treated equally when determining multiple conditions.
- `keywords` often contain general or redundant tokens like `"책 추천"` and shouldn’t be considered a strong filtering condition.
- Using `sum([bool(x), ...])` is a concise way to check how many fields are filled, but it must be used with carefully selected attributes.
- Precise tool routing logic is critical to ensure user queries are handled with the most relevant recommendation method.

##  Before vs After Fix

| Input Query                    | Tool Before Fix | Tool After Fix |
|-------------------------------|-----------------|----------------|
| `"소설 추천해줘"`                | `hybrid_tool`   | ✅ `genre_tool` |
| `"행복한 소설 추천해줘"`         | `hybrid_tool`   | ✅ `hybrid_tool` |
| `"천선란 작가 책 추천해줘"`      | `hybrid_tool`   | ✅ `author_tool` |

##  Goals for Tomorrow

- Add more tests and example cases to validate hybrid conditions (e.g., `author + emotion`, `genre + emotion`).
- Improve the relevance of `hybrid_tool` retrieval by refining the `query_summary` and filtering logic in the retriever.
