# 2025-06-15 Reflections: What I Learned from the Modeling Project

## What I did today
- Wrote a weekly blog post reflecting on my first modeling project
- Finalized and reviewed the ERD using ERD Cloud

## What I learned

### 🌱 Reflections on My First Team Modeling Project

- **The Value of Process:**  
  This project was my first hands-on experience with the full cycle of team-based modeling—from initial requirement analysis to ERD design, table creation, and actual implementation. I realized how important it is to follow the proper process step by step: requirements analysis, conceptual modeling, logical modeling, physical modeling, and testing.

- **Importance of Communication:**  
  Frequent team meetings, peer reviews, and feedback were crucial. There were many moments when I thought my way was the best, but discussions often revealed better approaches or flaws in my logic. Teamwork and communication made the model more robust.

- **Difficulties and Growth:**  
  I struggled with defining relationships between tables, especially when handling order details, option management, and history tracking (like for refunds/exchanges). I learned the hard way that seemingly simple requirements can have complex implications in DB design—especially when it comes to handling state changes and historical data.

- **Flexibility and Scalability:**  
  I understood the importance of designing for future requirements, not just current ones. For example, separating order status history and refund/exchange history made it easier to support partial refunds or future feature additions.  
  Keeping the model extensible prevents headaches later.

- **The Power of Visualization:**  
  Using ERD Cloud helped me visually identify missing relationships and redundant tables. It also made it easier to share and discuss my ideas with teammates.

- **Takeaways:**  
  - Don’t just focus on technical implementation; think about **why** you need each table and attribute.  
  - Always keep documentation up to date—good docs save time for everyone.  
  - Try to foresee possible future changes and design with flexibility in mind.  
  - Communication and feedback are as important as technical skills.
 
   ( This week's blog ; https://velog.io/@gkeuni/커널아카데미-백엔드-부트캠프-12주차-1차-프로젝트-회고 )

## Goals for tomorrow
- Study and implement CRUD operations in my project
- Start the new team project to build a website
