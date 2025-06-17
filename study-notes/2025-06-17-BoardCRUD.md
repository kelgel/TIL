# 2025-06-17 Board Read, Delete, and Update in Spring

## What I did today
- Participate in a team project to make a website and got a role to make a board
- Studied how to implement the read (view), delete, and update (edit) functionalities for a message board using the Spring Framework (MVC)
- Practiced writing controller, service, and DAO methods for each operation
- Tested these features in a web application with MyBatis and JSP

## What I learned

### 📝 Board Operations in Spring (Read, Delete, Update)

#### Reading (View) a Board Post
- Implemented a controller method to retrieve a single post by its ID.
- Used the service and DAO layers to fetch the post from the database.

#### Deleting a Board Post
- Implemented a delete function that allows users to remove posts by ID.
- Handled cases where the post might not exist or the user is not authorized to delete it.
- Ensured safe deletion with proper feedback and redirects after deletion. (send notifications)

#### Updating (Editing) a Board Post
- Created an edit page where users can update the content of an existing post.
- Fetched the current post data, displayed it in a form, and processed the update on submission.
- Implemented validation to prevent empty or invalid updates.

## Goals for tomorrow
- Add validation and error handling for all board operations
- Start to make a board for the team project
