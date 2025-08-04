# 2025-08-04 TIL - Understanding JWT Flow and Kicking Off My Spring Boot Board Project

## What I did today
- Studied the full flow of JWT authentication in Spring Boot.
- Analyzed key components like JwtAuthenticationFilter, JwtUtil, and how tokens are validated and parsed.
- Started my personal backend project for a scalable article board using Spring Boot and RESTful API design.
- Decided to use a clean architecture: rather than connecting Controller and Service directly to the entity, I introduced DTOs (PostRequestDto, PostResponseDto) for data handling.

---

## What I learned
- ### The JWT authentication process has 4 main steps:

  Client sends request with JWT in the Authorization header.

  JwtAuthenticationFilter intercepts the request and extracts the token.

  JwtUtil validates the token and extracts the userId.

  UserService uses the userId to retrieve the user and register them in the Spring Security context.

- ### The difference between:

  createToken() → used at login time.   
  getUserIdFromToken() → used when handling authenticated requests.

- The importance of using DTOs to separate domain entities from request/response structures, making the code cleaner and more maintainable.

---

## Reflections
- Breaking down each step of the JWT lifecycle made it easier to debug and extend the logic later.
- Chose to implement DTOs from the beginning—it feels more structured and scalable.

---

## Goals for Tomorrow
- Finish implementing PostService and its methods using PostRepository.
- Create and test the corresponding PostController.
- Add JWT-based authentication to the post-related endpoints (e.g., only allow authenticated users to create/edit/delete posts).
- Study how to return PostResponseDto properly with user nickname and date formatting.
