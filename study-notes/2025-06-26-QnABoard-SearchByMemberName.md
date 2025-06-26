# 2025-06-26 QnA Board – Search by Member Name & CSS Integration

## What I Did Today

- Improved and implemented front-end styling using CSS  
- Merged teammates’ branches and resolved Git conflicts  
- Updated search functionality to retrieve results by member name instead of member ID  
- Modified QnA post and comment display to show member names  
- Applied basic CSS styling to enhance layout and readability

---

## What I Learned

- ### Displaying Member Names Instead of IDs 
  Originally, `member_id` was set as a foreign key in the `qna` and `qna_answer` tables, and all displays used this ID.  
  However, we wanted to show the actual member **names** in the post and comment views.  
  To achieve this, I modified the SQL mappers to use `JOIN` statements to fetch user-friendly information.  
  Then, I updated the **mapper → DTO → DAO → Service → Controller → JSP (view)** layers in sequence to reflect the changes.  
  This experience helped me realize that foreign key relationships aren't the only way to access related data — using SQL joins can be a flexible and readable alternative when used wisely (keeping performance in mind).

- ### Merge Conflicts & Collaboration Challenges
  As with the previous day, we continued merging individual work into the main branch.  
  A major conflict occurred because two team members had created different versions of files with the same names.  
  Although each developer was working on different areas, this incident highlighted how **interconnected** every part of the project is.  
  We temporarily resolved the issue by renaming files and confirming functionality, but ultimately, this taught us that:
  - Effective **communication** is critical during collaborative development.
  - Agreeing on clear **file naming conventions and structure** in advance helps avoid conflicts.

- ### CSS Styling & Front-End Integration 
  Besides back-end tasks, I spent time improving the UI with basic CSS.  
  Although I'm focusing on back-end development, I found that some knowledge of front-end design is essential for building a complete and usable product.  
  Using online references and AI assistance, I was able to apply styling that made the interface more user-friendly.  
  This reminded me that understanding both front-end and back-end helps bridge the full-stack development experience.

---

## Goals for Tomorrow

- Add sidebar functionality and layout to the view pages  
- Review and clean up project code  
- Prepare for final project presentation
