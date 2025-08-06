# 2025-08-06 TIL – Seeding Test Data and Starting Elasticsearch Integration

## What I did today
- Used Faker to generate 10,000 seed posts for performance and search testing.
- Started integrating Elasticsearch with my Spring Boot project using spring-data-elasticsearch.
- Defined a new ES-specific document class: PostDocument.
- Set up Docker containers for Elasticsearch + Kibana and verified they are running locally.

---

## What I learned
- ### Seeding with Faker for Test Data
Faker is useful for early-stage testing, but its default output (faker.lorem()) generates meaningless Latin.  
-> Replaced the content generation logic with keyword-based sentence construction to simulate more realistic data.  
JPA maps String to VARCHAR(255) by default, so I had to change the content column type to TEXT to store full paragraphs.

- ### Post vs PostDocument
Post → MySQL entity  
PostDocument → ES-specific object used for indexing and searching  
ElasticSearch can't use MySQL entities as-is, so I defined a tailored schema (@Document(indexName = "posts")) for ES.

- ### Indexing Posts
Implemented PostIndexService to convert Post to PostDocument and save them in ES.  
Built a dedicated indexing API (POST /api/index) to trigger bulk indexing.  
Learned that indexing is a one-time operation (as long as the ES container is running).

---

## Reflections
- Generating meaningful test data is crucial for evaluating search quality later.
- I now understand how indexing separates the data layer (MySQL) from the search layer (ElasticSearch).
- Starting from a solid foundation like document modeling (PostDocument) will make later optimization easier.
  
---

## Goals for Tomorrow
- Complete the search API using PostDocumentRepository with keyword matching on title and content.
- Test search speed and result quality using Postman and Kibana.
- Add pagination and relevance sorting to the search results.

