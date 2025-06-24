# 2025-06-23 QnA Board Search Feature

## What I Did Today

- Implemented search functionality for the QnA board.
- Reviewed and received feedback on database modeling (Order domain).
- Updated and refined ERD diagrams using ERD Cloud. (Still Working on)

---

## What I Learned

- **Developed Flexible Search Functionality with Dynamic SQL**  
  I built a dynamic search feature on the QnA board that lets users search posts by title, content, or writer.
  Implementing the dynamic SQL conditions in MyBatis taught me how to use `<choose>`, `<when>`, and `<otherwise>` to handle flexible query requirements.
  This improved user experience, as users can select whether to search by title + content, only title, or writer.

- **What is a REST API?**  
  REST(Representational State Transfer) API is an architectural style for building web services that use standard HTTP methods (GET, POST, PUT, DELETE) to allow different systems to communicate over the internet.
  Each URL represents a resource (such as a QnA post), and the methods define what kind of operation should be performed (fetching, creating, updating, or deleting).  
  For example, in the QnA board,  
  - `GET /qna/list` fetches the list of posts  
  - `POST /qna/write` creates a new post  
  - `PUT /qna/{id}` updates a post  
  - `DELETE /qna/{id}` deletes a post  
  This separation makes APIs intuitive, scalable, and easy to maintain.

- **When to use springify() and parse()**  
  - `springify()` is generally used to adapt or process objects, values, or data structures so that they're compatible with Spring conventions or frameworks.
    For example, it can be used to convert raw data into Spring Beans, DTOs, or property formats before injecting or processing them in the application.  
  - `parse()` is commonly used whenever there is a need to convert formatted data (such as String) into another type—such as converting a `String` to an `int`, a `Date`, or a domain object.
    In a REST API or form submission, input from users is often received as a String and must be parsed to the correct type before usage or validation.

---

## Goals for Tomorrow

- Add comment functionality to QnA posts.
- Implement a "secret post" (private) feature with password for sensitive questions or answers.
