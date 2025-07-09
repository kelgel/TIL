# 2025-07-09 TIL Java03 & mindest

## What I Did Today

- Participated in a special lecture on developer mindset and continuous growth.   
      *Reflected on the phrase:* **“Studying brings about the result of not being afraid.”**
- Reviewed Spring Boot topics like Thymeleaf and Reflection API.
- Debugged a CSS issue caused by an outdated dependency version.
- Revisited the difference between Filter and Interceptor in Spring.
- Learned Java operators (Chapter 3): arithmetic, logical, ternary, and more.

---

## What I Learned

- ### 🔍 Reflection API
  - Part of `java.lang.reflect` package.
  - Allows runtime inspection and manipulation of class structures (fields, methods, constructors).
  - Frameworks like Spring use it heavily for dependency injection and annotations.

- ### 🔢 Spring Boot Notes

  | Concept | Description |
  |--------|-------------|
  | Filter | Runs outside Spring container; cannot access beans. |
  | Interceptor | Runs inside WebApplicationContext; supports bean injection. |
  | RedirectAttributes | Inherits Model features + supports flash attributes. |
  | Redirect vs Forward | Redirect = new request/response (URL changes); Forward = same request (URL stays). |
  
  (+) Importance of verifying dependency versions when debugging frontend issues (like CSS not loading).

- ### ☕ Java Operators (Chapter 3)
  
    | Type | Operators | Notes |
    |------|-----------|-------|
    | Arithmetic | `+`, `-`, `*`, `/`, `%` | Integer division truncates |
    | Comparison | `>`, `<`, `==`, `!=` | Returns boolean |
    | Logical | `&&`, `||`, `!` | Combine or negate conditions |
    | Ternary | `cond ? A : B` | Inline if-else |
    | Assignment | `=`, `+=`, `%=` | Updates variables |
    | Increment | `++`, `--` | Pre vs Post matters |
  
   - Logical negation and De Morgan's Law apply: !(x > 0 && y < 10) becomes x <= 0 || y >= 10.      
   - Post-increment (i++) vs Pre-increment (++i) differ in the order of execution.

---

## Reflection
- Even seemingly small issues like dependency versions can affect application behavior. Always verify compatibility.   
- Spring’s internal mechanisms like interceptors and the Reflection API add powerful functionality, but need further practice to master.   
- Learning software engineering isn’t just about writing code — it’s about understanding the entire development process, from planning to testing.   
- *Consistent studying builds not only skill, but also the confidence to face the unknown*.   

---

## Goals for Tomorrow
- Continue Java review: Chapter 4 (Control Statements).
- Deepen understanding of Thymeleaf syntax and its dynamic behavior.
