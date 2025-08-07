# 2025-08-07 TIL – Implementing and Debugging Elastic Search

## What I did today
- Tried implementing searchByElasticsearch() method to replace MySQL-based search.
- Simple postman test - MySQL version worked as expected.
- Encountered decoding error when handling SearchResponse<PostDocument> from Elasticsearch. Still working on the fix.

---

## What I learned
- ### 🔄 Elasticsearch Query Flow
```
PostSearchRequestDto
  ↓
[title, content] → match query  
[author] → term filter  
[regDate] → range filter  
  ↓
Combined using boolQuery (must + filter)  
  ↓
ElasticsearchClient.search()  
  ↓
SearchResponse<PostDocument>  
  ↓
Mapped to List<PostResponseDto>
```

- ### 📦 Understanding SearchResponse<T>
The Elasticsearch Java API wraps search results in SearchResponse<T>, which contains:
hits().total().value() → Total number of matching documents
hits().hits() → List of SearchHit<PostDocument>
hit.source() → Actual document content
hit.score() → Relevance score
hit.highlight() → Highlighted text (if applied)

- ### 🔍 Overview of Key Elasticsearch Queries
 
| Type            | Query          | Use Case                             |
| --------------- | -------------- | ------------------------------------ |
| **Text Match**  | `match`        | Natural language search              |
| **Exact Match** | `term`         | Precise value match (e.g. author ID) |
| **Range**       | `range`        | Date or numeric filtering            |
| **Boolean**     | `bool`         | Combine multiple conditions          |
| **Multi-field** | `multi_match`  | Search same keyword across fields    |
| **Highlight**   | `highlight`    | Emphasize matched text in results    |
| **Advanced**    | `query_string` | Lucene query language (rarely used)  |

---

## Reflections
I got more familiar with how Elasticsearch queries are built and executed in Java. The layered structure of queries (match, term, range → bool → client.search) became clearer. However, handling the response format and mapping it correctly to DTOs still needs debugging.

---

## Goals for Tomorrow
- Fix SearchResponse decoding error
- Finish Elasticsearch-based search fully
- Refactor MySQL/ES search logic into reusable methods

