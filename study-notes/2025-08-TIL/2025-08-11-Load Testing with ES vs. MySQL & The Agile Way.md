# 2025-08-11 TIL – Load Testing with ES vs. MySQL & The Agile Way

## What I did today
- Conducted a series of performance tests comparing Elasticsearch (ES) and MySQL, focusing on cache effects and handling different load scenarios (spike and soak).
- Spent time learning about the principles of Agile methodology.

---

## What I learned
- ### Cache Effects (Cold vs. Warm):

ES showed a significant performance jump (up to 68%) after the initial query, proving that a pre-warming strategy is essential after deployment.

MySQL's cache showed some volatility, suggesting that a brief warm-up period is good for stability.

- ### Spike Test (Sudden Load):

Under a sudden traffic spike (300 concurrent users), ES was ~6 times faster than MySQL, ensuring a better user experience during peak events.

- ### Soak Test (Sustained Load):

MySQL was slow but incredibly stable with a 0% error rate.

ES achieved a very high throughput but had a high error rate of 65% under prolonged stress. This shows a clear need for performance tuning for long-term stability.

- ### Agile Methodology:

Agile is a flexible, iterative approach to development. 
Instead of building a perfect solution all at once, you deliver in small increments, test frequently, and adapt based on continuous feedback. 
This mindset is about embracing change and focusing on delivering value quickly.

---

## Reflections
The tests highlighted a classic trade-off: ES for speed and concurrency, and MySQL for stability and durability. My takeaway is that a single system often isn't the complete answer. The best approach is to design an architecture that leverages the strengths of both. 
For example, using ES for the main search functionality for its speed, but building a fallback to MySQL when ES is under critical stress. 
This process of testing, analyzing the results, and adapting our architectural plan is a perfect example of the Agile mindset in action—iterating and improving based on real-world data.

---

## Goals for Tomorrow

- Install and connect Redis for test
- Keep working on CV
