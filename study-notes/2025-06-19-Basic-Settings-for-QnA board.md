# 2025-06-19 Basic Settings for QnA board

## What I did today
- Set up basic DAO, DTO, mapper, and JUnit test files for the QnA board using Spring and MyBatis

## What I learned

### MyBatis CamelCase Mapping
- MyBatis did not automatically map snake_case DB columns (like `qna_id`) to camelCase Java fields (`qnaId`), causing all fields to be `null` in DTOs.
- Fixed this by adding `<setting name="mapUnderscoreToCamelCase" value="true"/>` to `mybatis-config.xml`, which resolved the mapping and test errors.

### NOT NULL Constraints in DB and Code
- Initial tests failed because I omitted columns required by NOT NULL constraints in the DB schema.
- Learned that all NOT NULL fields must be included when inserting/updating data, even during testing.

### Foreign Key Constraint Issue
- Encountered an FK error when adding a constraint between `qna.member_id` and `member.member_id` due to mismatched IDs.
- Fixed by updating `qna.member_id` values to existing IDs in the member table, then successfully added the foreign key.

### Practical Tips
- Always align DB constraints with your code and test data.
- Use MyBatis and database settings carefully to avoid common mapping and constraint errors.
- Check constraint status with SQL queries on `information_schema` as needed.

## Goals for tomorrow
- Implement paging and post creation features for the QnA board
