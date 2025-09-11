# 2025-09-11-TIL MyBatis Mapper Issues & Fixes

## What I Did Today

- Investigated recurring MyBatis mapper-related errors affecting Spring Boot startup.
- Fixed multiple issues:
  Updated @MapperScan to cover the entire package instead of only domain.
  Added missing @Mapper annotations.
  Standardized mybatis.mapper-locations to handle both mappers/ and mappers.domain/.

---

## What I Learned

- MyBatis fails application startup if any single XML mapper is missing or malformed.
- Inconsistent package scanning (@MapperScan) was a key root cause for missing mapper beans.
- Standardizing mapper-locations and XML folder structure improves stability.
- Using clean builds after Devtools hot-reloads avoids cached mapper conflicts.

---

## Reflections

- Small misconfigurations in MyBatis can cascade into application-wide failures.
- Consistency in package naming, XML locations, and mapper registration is crucial for maintainability.
- Learned the importance of enforcing a project-wide mapper configuration standard early.

---

## Goals for Tomorrow

- Finalize MyBatis configuration by:   
  Consolidating all XML mappers into src/main/resources/mappers/.  
  Cleaning up unused or placeholder XML files.   
  Implement integration tests to verify that all mappers are registered and functional.   
