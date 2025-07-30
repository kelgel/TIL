# 2025-07-30 TIL — Tool Based RAG Search & Output Consistency Between CLI and Web

## What I Did Today

- Implemented a feature to include product detail page URLs using the book’s ISBN.
- Debugged errors related to improper Document access and missing List import in formatters.py.
- Investigated why CLI output and web API response render differently.
- Confirmed that Markdown is displayed as raw text unless explicitly rendered on the frontend

---

## What I Learned

| Topic                         | Key Insight |
|------------------------------|-------------|
| 🧩 **File Modularization**   | Split responsibilities into `tools/`, `utils/`, and `prompts/` folders to keep the project clean and maintainable. For example, `emotion_tool.py`, `formatters.py`, and `emotion_prompt.py` each have their own concern. |
| 🔗 **ISBN-based URL generation** | Built dynamic product detail URLs using `isbn` in metadata: `http://localhost:8080/product/detail?isbn=...`. Ensured URLs are clickable in both terminal and web environments. |
| 📄 **LangChain Document Access** | `Document` objects from Chroma don’t support `.get()`. Instead, access with `doc.page_content` and `doc.metadata['isbn']`. |
| ⚠️ **Markdown Display** | Markdown output like `**bold**` or `[link](URL)` may render differently depending on where it's printed. Terminals support basic formatting; web clients need Markdown parsing libraries. |
| 🛠️ **Tool-Based RAG Search** | Implemented a full RAG-style flow inside the `emotion_tool`, including vector search and LLM response formatting. Verified that each tool can encapsulate search logic + prompt-driven generation. |

---

## Goals for Tomorrow

- Apply the same formatting logic to genre_tool, keyword_tool, and hybrid_tool.
- Refactor the frontend to support Markdown rendering in chat responses.
- Review and document the current prompt-response pipeline with sample data for better debugging and maintenance.
