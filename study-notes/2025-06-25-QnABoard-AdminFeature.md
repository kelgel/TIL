# 2025-06-25 QnA Board Admin Feature

## What I Did Today

- Implemented admin account access to manage posts.
- Merged with teammates' branches and resolved conflicts.
- Connected login and user domain to QnA using session information.

---

## What I Learned

- **Admin Account Design**

  Initially, I thought the admin account should be handled separately with a distinct management system since it has special permissions.    
  However, I realized that admins can be treated just like regular members by registering them with a predefined ID and password.   
  Then, we can distinguish them and grant privileges using a method like `isAdmin`.

- **Git Merge and Conflict Resolution**

  One of my biggest fears during team projects has been merge conflicts after pushing and merging code.  
  Today, I had to merge my branch with those of other teammates. Although I was worried, I learned that resolving merge conflicts calmly, step by step, is not as intimidating as I thought.   
  This was one of my first real merge experiences in a team setting. I also didn’t want to negatively affect the project, so I asked my teammates for help and solved the issues one by one.   
  This made me realize that understanding Git is essential for collaboration, and I plan to study it more deeply.

- **Session-Based Login Integration**

  While developing the QnA domain, I initially set `member_id` as a foreign key in the QnA table and manually injected the ID for testing.   
  After merging with the login domain, I had to retrieve login information from the session.   
  I thought it would be simple to get the `member_id`, but since the QnA domain was not connected to the login system, I needed additional components.   
  To properly integrate the two, I added the necessary DAO, DTO, and Mapper files to pass the `member_id` from the login function into the model, so that the QnA module can freely use it.
  

---

## Goals for Tomorrow

- Improve and implement the front-end design.
