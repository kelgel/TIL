# 2025-08-12 TIL – Implementing Popular Posts & View Count Caching with Redis

## What I did today
- Integrated Redis into the project for caching post view counts and popular posts.

- Configured CacheConfig and updated PostService to clear search caches when posts are created, updated, or deleted.

- Implementing logic to increment view counts in Redis instead of hitting the database directly.

---

## What I learned
- ### Why cache view counts in Redis:
Updating the database on every page view is expensive under high traffic.
Using Redis to store temporary increments (deltas) drastically reduces DB writes and improves performance.

- ### Delta + periodic flush pattern:
Store increments in Redis (post:views:delta:{id}) and periodically merge them into the DB (views = views + delta).
This approach avoids double counting by resetting the delta to 0 after flushing.

- ### Key naming strategy:
Prefixes like post:views:{id} and post:views:delta:{id} make keys self-descriptive and easy to search with SCAN.

---

## Reflections
Today’s work showed me how caching can drastically change the performance profile of a feature like "popular posts."
Instead of hammering the database with each view, Redis handles the fast, volatile data while the DB remains the reliable long-term store.
The delta flushing design is a great example of balancing speed and consistency.

## Goals for Tomorrow
- Expose an endpoint to retrieve top N popular posts from Redis.

-  Add monitoring for Redis cache hit/miss and scheduled task performance.
