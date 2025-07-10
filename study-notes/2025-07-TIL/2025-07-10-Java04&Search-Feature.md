# 2025-07-10 TIL Java Conditionals & Loops / Search Feature

## What I Did Today
- Searched for internships and job opportunities I can apply to
- Set small goals for ongoing and future projects
- Implemented the search feature in the admin book list (Spring Boot assignment)
- Reviewed Java Chapter 4: Conditional and Loop Statements

---

## What I Learned Today
- ### ☕ Java Conditionals & Loops (Chapter 4)
🔹 Conditional Statements
    if: Allows complex logical conditions and ranges

🔹switch: Simpler for fixed values like int, char, String
    → Be careful: without break, fall-through occurs

🔹 Loop Statements

  | Statement  | Checks condition first | Executes at least once |
  | ---------- | ---------------------- | ---------------------- |
  | `while`    | ✅                      | ❌                      |
  | `do-while` | ❌                      | ✅                      |

(+) Tips
- if vs switch: Use if for range conditions, switch for fixed values
- do-while: Use when at least one execution is required
- Be careful where you initialize variables in loops

- ### 📘 Thymeleaf Basics
    - ✅ 1. ${...} – Expression Syntax    
    Used to access model attributes from the Spring controller  
    `Example: ${book.title} → accesses title from the book object in the model`

    - ✅ 2. <th:block> – Logic Block (Not Rendered)     
    Acts as a logical wrapper that does not appear in HTML output      
    Used for conditional display or grouping elements

        ```
        <th:block th:if="${#lists.isEmpty(books)}">
        <p>No results found.</p>
        </th:block>
        ```

    - ✅ 3. th:if & th:unless – Conditional Rendering       
    `th:if`: renders element only if condition is true      
    `th:unless:` renders element only if condition is false

        ```
        <p th:if="${user != null}">Welcome, user!</p>
        ```

---

## Goals for Tomorrow
- Add pagination and sorting to the book list page
- Review Java Chapter 5 (Arrays)
