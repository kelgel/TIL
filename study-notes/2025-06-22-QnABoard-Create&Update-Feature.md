# 2025-06-22 QnA Board Update and Create Feature

## What I Did Today

- **Implemented update and create functionalities for the QnA board**  
  Enabled users to write new posts and update existing ones on the QnA board. This involved adding and connecting the necessary service and controller methods to handle create (`write`) and update (`modify`) features. 

- **Uploaded weekly blog**  
  Shared my weekly blog as part of my regular development reflection.   
  https://velog.io/@gkeuni/커널아카데미-백엔드-부트캠프-13주차-토이-2차-프로젝트-회고

---

## What I Learned

- **Separation of concerns in Spring MVC**  
  Revisited best practices for maintaining clear boundaries between controller, service, and DAO layers. Each layer was responsible for its own distinct logic, which makes the codebase maintainable and clear.

- **Efficient handling of create and update operations**  
  Learned to manage differences and similarities between insert and update flows within the application. Improved my understanding of parameter binding, DTO usage, and aligning backend logic with MyBatis mapper statements.

- **Providing user feedback and redirection**  
  Applied success and error message handling after create and update actions using Spring MVC’s RedirectAttributes and Model, which enhances user experience on the front end.

- **Unit testing of data persistence**  
  Confirmed correct implementation by writing transactional tests for the DAO layer, ensuring that both insert and update operations work reliably with automatic rollbacks.

- **Unit testing and the importance of validation**  
  Wrote and reviewed various JUnit test cases while developing. This process highlighted how crucial testing is for catching edge cases and oversights that might be missed during initial development. Writing test cases required me to think more deeply about possible scenarios, and running these tests revealed parts of the logic I hadn't considered at first. Overall, I recognized that good test coverage is essential for building robust and reliable features, and that careful validation through testing helps ensure the application's quality.

---

## Goals for Tomorrow

- **Implement search functionality**  
  Allow users to search QnA posts by keywords and filter options, utilizing the `SearchCondition` DTO for improved usability.

- **Add comment feature**  
  Plan to introduce the ability for users to write comments on individual QnA posts for improved interaction and discussion.

---
