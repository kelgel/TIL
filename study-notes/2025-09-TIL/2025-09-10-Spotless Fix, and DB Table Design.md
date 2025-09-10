# 2025-09-10-TIL Spotless Fix, and DB Table Design

## What I Did Today

- Added today's tasks to GitHub Issues for better tracking.
- Resolved a CI/CD build failure caused by Spotless formatting errors:
  Pulled the latest branch and added the plugin → id 'com.diffplug.spotless' version '6.25.0'.
- Applied fixes using ./gradlew spotlessApply.
- Created Oracle DB tables for the AI content pipeline and started writing MyBatis mappers to integrate with Spring Boot.

---

## What I Learned

- Learned how to troubleshoot Spotless plugin errors and ensure proper CI/CD formatting compliance.
- Understood the importance of maintaining consistent code style rules across the team.
- Reviewed database design strategies for managing AI content generation flows.

---

## Reflections

- Debugging the build failure highlighted the value of CI/CD automation for catching issues early.
- Deciding on the right level of table normalization is critical to balance MVP simplicity and future scalability.

---

## Goals for Tomorrow

- Finalize the ERD for the AI-related tables:
  AI_REQUEST → snapshot of input & deduplication keys.
  AI_GENERATION → prompt/model metadata, latency, success/failure state.
  AI_POST → generated content snapshot.

- Complete MyBatis mapper implementations for CRUD operations.
