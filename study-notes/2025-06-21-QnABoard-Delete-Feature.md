# 2025-06-21 QnA Board Delete Feature

## What I Did Today
- Implemented the delete functionality for QnA board posts.
- Adjusted request handling to work without a login session.
- Debugged a MyBatis parameter binding issue.

---

## What I Learned

### **Controller ↔ MyBatis Parameter Mapping Issue**
While developing the delete feature, I encountered an issue where the `qnaId` parameter wasn't properly mapped in MyBatis. After investigation, I realized it stemmed from how the `memberId` was being passed.

Originally, the controller relied on session-based authentication to inject the `memberId`. However, since the current flow assumes a user is already logged in (without a login page), the session was never populated—causing MyBatis to throw a mapping error due to missing parameters.

To address this, I changed the flow to explicitly receive the `memberId` via `@RequestParam`, rather than through the session.

---

### **Importance of `@Param` in MyBatis**
I ran into the following error while calling the `delete()` method:
org.apache.ibatis.binding.BindingException: Parameter 'count' not found. Available parameters are [arg1, arg0, param1, param2]

This clearly indicated that MyBatis was not able to map the named parameters because they weren't explicitly annotated. Adding the `@Param` annotation solved the problem:

```java
int delete(@Param("qnaId") Integer qnaId,
           @Param("memberId") Integer memberId) throws Exception;
```
Lesson learned: Always use @Param in mapper interfaces when dealing with multiple parameters, even if they seem obvious.

---

### **Session Usage Strategy**
In a real login environment, it makes sense to fetch the memberId from the session. But since we're assuming users are authenticated (for development simplicity), passing memberId directly as a request parameter is more reliable for now.

This highlighted an important architectural point: Session handling should be consistent and aligned with the current login/auth approach.

---
## Goals for Tomorrow
- Implement update and create (write) functionalities for the QnA board.
- Begin preparing tests for basic QnA operations (CRUD).
