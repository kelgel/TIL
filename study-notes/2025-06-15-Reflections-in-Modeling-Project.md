# 2025-06-15 Reflections: What I Learned from the Modeling Project

## What I did today
- Wrote my weekly blog post reflecting on the modeling project
- Finalized and reviewed the ERD using ERD Cloud

## What I learned

### 🌱 Reflections & Lessons Learned

During this project, I realized that concepts which felt abstract during theoretical study became much clearer once I actually experienced each step of the modeling and design process. By being responsible for a specific domain (in my case, the order system in a shopping mall), I gained hands-on understanding of how different entities and tables are connected in practice.

**Trial and Error:**  
One area that initially confused me was whether to store detailed product option information (such as color, size, quantity, unit price, and actual purchase price) directly in the `OrderDetail` table or simply reference the product table.  
After discussion and research, I learned it is essential to store these attributes in the `OrderDetail` table.  
**Why?**  
- Product information can change over time (options added/removed, price fluctuations, etc.)
- The “option/size/quantity/price” at the moment of ordering must be historically recorded  
- If this information is not stored, it becomes impossible to accurately reproduce past orders after product options or prices change  
- This can lead to critical issues in accounting, customer inquiries, and support

Another point of confusion was whether to store information such as the delivery address and payment method directly in the order table. Initially, I assumed everything visible on the UI or in the screen specification needed to be stored separately in the database.  
However, after careful study and reflecting on the actual purpose of each table, I realized only the attributes truly relevant to the order entity need to be stored there. For example, the payment method can be referenced from the payment table via a foreign key and joined when needed, rather than duplicating it in the order table.  
This project taught me that good database design is not just about what to store, but also about how to display and retrieve data effectively.

I wouldn’t have gained these insights if I hadn’t gone through the actual design process. I made many mistakes along the way, and there are still parts I want to improve, but I feel my understanding of data modeling and entity relationships has deepened. Above all, I learned the value of constant communication with my teammates and how much we can grow by sharing and reflecting together.

---

### 📝 My KPT Retrospective

**Keep (What I want to continue):**
- Proactively sharing issues or uncertainties with my team instead of struggling alone.
- Arriving early (before 9 AM) every day to prepare and stay on track.

**Problem (What was difficult):**
- Since the project covered topics I had missed in class, it took a lot of time at first to find the right direction and fill knowledge gaps.
- On days when I couldn’t concentrate, my productivity dropped noticeably.

**Try (What I want to try next time):**
- Before starting a project, I want to make sure I review key concepts so I can work more smoothly and accelerate my growth.
- If I find myself unable to focus, I’ll try taking a short walk or break to clear my mind and refresh my energy.

   ( This week's blog ; https://velog.io/@gkeuni/커널아카데미-백엔드-부트캠프-12주차-1차-프로젝트-회고 )


---

## Goals for tomorrow
- Study and implement CRUD functions in my project
- Start the new team project to build a website

  
