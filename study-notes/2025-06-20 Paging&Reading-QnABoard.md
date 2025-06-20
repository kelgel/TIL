# 2025-06-20 Paging and Reading QnA Board

## What I did today
- Used JUnit tests to insert and delete QnA data directly in the database
- Implemented pagination and made post titles clickable links for detail views
---
## What I learned
- **Spring Bean Injection & Configuration:**  
  I faced an issue where my DAO was not injected properly as a Spring bean, causing runtime errors.  
  By reviewing the XML configuration and code annotations:
    - I added the `@Repository` annotation to my `QnaDao` interface to let Spring recognize it as a bean.
    - In `root-context.xml`, I set up the `MapperScannerConfigurer` to scan the correct base package and register beans with the `@Repository` annotation.
    - I made sure both the `dao` and `mapper` packages were included in the configuration.
  Through this process, I learned how Spring and MyBatis work together for bean discovery and dependency injection.

- **Understanding the Full Flow (DB → Repository → Service → Controller):**  
  By incrementally developing each feature, I gained a much clearer understanding of how data flows through a typical Spring web application:
    - **Database:** Stores QnA data.
    - **Repository (DAO):** Handles low-level data access using MyBatis mappers.
    - **Service:** Contains business logic and mediates between controllers and DAOs.
    - **Controller:** Processes HTTP requests, interacts with the service layer, and passes data to JSP views.
  Testing insert/delete operations via JUnit made it easier to verify each layer separately, while debugging paging and detail view features helped me see how information moves step-by-step through the system.

- **Incremental Feature Development:**  
  Building the application feature by feature (starting with data access, then paging, then linking posts to detail pages) reinforced the importance of a step-by-step, test-driven approach.  
  It was helpful to see how making one part of the system work (like fixing bean injection) can enable the rest of the workflow to function as intended.
---
## Goals for tomorrow
- Finalize the delete feature and implement update and create (write) features for the QnA board
