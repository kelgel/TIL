# 2025-08-08 TIL – JMeter Performance Testing & Elasticsearch Decoding Error Fix

## What I did today
1. Ran three JMeter performance test scenarios:
   - Keyword-based search performance (MySQL only)
   - MySQL vs Elasticsearch search under equal load (endpoint comparison)
   - User load scaling tests with varying thread counts
2. Collected and analyzed test results, focusing on Average Response Time and Throughput.
3. Investigated and resolved `Failed to decode response` error from Elasticsearch search API.

---

## What I learned

### 🧪 JMeter Test Scenarios Implemented

| **Test Name**                          | **Purpose** |
|----------------------------------------|-------------|
| Keyword Search Test                    | Measure search performance using keyword dataset (`keywords.csv`) |
| MySQL vs Elasticsearch Comparison      | Compare average latency and throughput under identical conditions |
| User Load Scaling Test                  | Observe system behavior under increasing concurrent users |


### 📊 Key Observations from Today's Tests
  - MySQL search consistently showed higher average latency under heavy load compared to Elasticsearch.
  - Elasticsearch handled concurrent requests more evenly, with better throughput stability.
  - Keyword-based search showed linear latency growth with increased user threads.

### 🐛 Elasticsearch Decoding Error – Root Cause & Fix
  Error Message:   
  java.lang.RuntimeException: Elasticsearch search error: node: http://localhost:9200/, status: 200, [es/search] Failed to decode response
  
  Root Cause:    
  - Spring Data Elasticsearch automatically adds `_class` field in `_source`.
  - PostDocument class did not have `_class`, causing Jackson deserialization failure.
  - regDate field had variable formats (`2025-08-06T11:06:55.948725` vs `2025-08-06T11:06:55Z`) leading to parsing errors with LocalDateTime.
  
  Fix Applied:   
  - Added `@JsonIgnoreProperties(ignoreUnknown = true)` to PostDocument to ignore unexpected fields.
  - Changed regDate type from `LocalDateTime` to `String`, parsing manually in DTO conversion.
  - This combination ensured all responses could be processed without decoding failure.

---

## Reflections
Today I got hands-on experience running multiple performance testing scenarios in JMeter and comparing MySQL vs Elasticsearch behavior. I also resolved a tricky decoding issue in the ES Java API by making PostDocument more tolerant to unexpected fields and variable date formats. This improved both system stability and test reliability.

---

## Goals for Tomorrow
- Implement Cold vs Warm cache performance measurement for MySQL and Elasticsearch.
- Generate performance graphs from JMeter result CSVs for documentation.
- Refactor test plans to allow easier endpoint switching.
