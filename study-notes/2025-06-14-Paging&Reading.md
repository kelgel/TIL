# 2025-06-14 Paging and Reading 

## What I did today
- Studied how to implement paging and data reading features using the traditional Spring Framework 
- Wrote codes for displaying data with **numbered pagination** (page numbers shown at the bottom of the page, e.g. [1][2][3][4][5])
- Implemented controller, service, and DAO logic to support efficient paging and page navigation
- Used JSP and MyBatis to retrieve paginated data and display pagination controls in the view

## What I learned

### 📝 Paging and Numbered Pagination in Spring

#### Importance of Numbered Pagination
- Numbered pagination is essential for user-friendly navigation in web applications, allowing users to jump to specific pages quickly (e.g. clicking on page numbers [1][2][3]...).
- It improves both usability and performance by preventing excessive data loading and giving clear navigation feedback to users.

#### Implementing Numbered Pagination with Spring MVC and MyBatis
- Developed controller logic to calculate the total number of pages based on total record count and page size.
- Passed necessary paging data (current page, total pages, page numbers to display, etc.) from the controller to the JSP view.
- In JSP, dynamically rendered pagination controls: previous/next buttons and a list of page numbers.
- Wrote MyBatis SQL queries using `LIMIT` and `OFFSET` to fetch only the records for the current page.

## Goals for tomorrow
- Study and make CRUD function in my project
- Write the weekly blog
