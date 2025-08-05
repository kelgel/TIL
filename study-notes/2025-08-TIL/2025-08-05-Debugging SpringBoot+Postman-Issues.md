# 2025-08-05 TIL - Debugging Spring Boot + Postman Issues

## What I did today
- Tested post API using Postman
- Investigated issues where DB updates didn’t reflect despite 200 OK
- Improved entity default settings and Swagger UI access
- Implemented Controller and added paging

---

## What I learned
- ### 1. POST/PUT not reflected in DB
Cause: Missing @Transactional → No commit    
Fix: Added @Transactional to service methods

- ### 2. NullPointerException on .intValue()
Cause: views field was null    
Fix: Set default value (0) in entity

- ### 3. Insert error due to isDeleted = null
Cause: No default value for non-nullable field    
Fix: Initialized to false

- ### 4. @Builder ignored default values
Cause: Lombok doesn’t apply field defaults in @Builder   
Fix: Used @Builder.Default annotation

- ### 5. Postman OK ≠ DB saved
Lessons learned:  
Check for missing @Transactional   
Ensure dirty checking is triggered    

- ### 6. Swagger UI blocked
Cause: Spring Security blocking Swagger routes   
Fix: Whitelisted Swagger paths in SecurityFilterChain

---

## Reflections
Even if the API returns a success status, DB changes may not happen if transactions or dirty checking are missing. Understanding the full request lifecycle is crucial.

---

## Goals for Tomorrow
- Finalize Swagger annotations across all controllers/DTOs
- Keep implementing sorting and searching features

