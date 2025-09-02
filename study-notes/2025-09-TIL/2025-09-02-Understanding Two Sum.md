# 2025-09-02 TIL – Understanding Two Sum

## What I Learned Today

- The Two Sum problem requires returning the indices of two numbers that add up to the target, not just the values.
- Brute Force Approach (O(n²)): check all pairs with nested loops.
- HashMap Approach (O(n)): store visited numbers in a map and check if the complement (target - x) already exists.

Key concepts:
- HashMap basics (put, get, containsKey).
---

## What I Did

- Implemented a first attempt at Two Sum (value-based, incomplete).
- Rewrote the solution using Brute Force for clarity.
- Optimized the solution with a HashMap approach.
- Reviewed when to use HashMap vs Two Pointers.
- Summarized key differences and reasoning.

---

##  Reflections

My initial solution logic was partially correct but missed the index requirement.
Realized that reading the problem constraints carefully is as important as writing code.
Learned why HashMap is a natural fit when we need fast lookup of complements.
Practicing both brute force and optimized solutions helps me understand trade-offs better

---

## Goals for Tomorrow

- Solve 2–3 more Easy LeetCode problems (arrays & hashmaps).
- Write both brute force and optimized solutions for each.
- Start practicing with debugging prints to trace logic.
- Summarize patterns (e.g., “when to use HashMap, when to use Two Pointers”).

