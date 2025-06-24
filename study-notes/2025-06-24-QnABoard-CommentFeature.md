# 2025-06-24 QnA Board Comment Feature

## What I Did Today

- Implemented comment and reply functionality for the QnA board.

---

## What I Learned

- **Issues Related to Defining Foreign Keys (FK)**
  - When adding new tables and columns from my local database to the team database, I encountered problems while defining foreign keys.    
    In my local test environment, foreign keys were easy to specify and test because I didn’t need to consider relationships with other tables actively used by my teammates.
    However, in the team DB, relationships such as references to `member_id` in the member table or `qna_id` in the qna table became tricky.
    There were already existing data or mismatched table states, which caused foreign key creation to fail.
    For the qna table, I had to remove all test data and recreate foreign keys because there were too many existing records that caused constraints to fail.
    As for the member table, there was not much test data, so I was able to add some rows and define foreign keys more easily.
    When creating tables based on the initial design (before inserting data), I never faced this issue because the tables were empty.
    Through today’s experience, I learned how to handle such cases in a real team environment.

- **Constructor Injection**
  - Constructor injection is more advantageous than field injection (@Autowired) as it becomes easier and faster to recognize any missing dependencies at compile time.
  - For this board implementation, I used field injection, but I plan to switch to constructor injection in my next project for improved maintainability and clarity.

- **Implementing the Comment Feature**
  - In contrast to the board functionality—where updating usually means changing full items—the comment and reply features only require updating the relevant part of the data. So, I implemented them using `@RestController`.
  - I developed the front-end with AJAX and JavaScript to interact with the backend via JSP. This was my first time using this approach, so some parts were quite challenging and complex.
  - I realized the need to study JavaScript further so I can organize and improve my code more effectively in the future.

---

## Goals for Tomorrow

- Implement admin account access to manage posts.
- Improve and implement the front-end (design).
