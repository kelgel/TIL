# 2025-08-19 TIL – Redis Cache Experiment and Performance Analysis

## What I did today

- Implemented Redis caching for post views in the Scalable Article Hub project.

- Ran JMeter tests with different access patterns (hot IDs, random IDs, Zipf distribution).

- Compared Cold Cache (Redis empty) vs Warm Cache (Redis pre-populated).

---

## What I learned

- ### Cache Hit Ratio and Workload Distribution

  Hot IDs (frequently accessed subset) → produced the highest hit ratio, showing cache is effective for skewed workloads.
  
  Random IDs → hit ratio stabilized around 50%, confirming cache effectiveness is workload-dependent.
  
  Zipf distribution → realistic scenario, with ~70–80% hit ratio, aligning with typical web workloads.

- ### Cold vs Warm Cache

  Cold cache runs had lower initial performance since Redis had to populate entries.
  
  Warm cache showed stable high hit ratios and faster response times.
  
  Reinforced the importance of pre-warming caches in production systems.

---

## Reflections

Different access patterns drastically affect cache efficiency → workload design matters as much as cache design.

Visualizing metrics (hit ratio) makes it easier to explain performance benefits.

---

## Goals for Tomorrow

- Document a before vs after performance chart for inclusion in the final project report.
