# 2025-08-20 TIL – CRUD Load Baseline & Capacity JMeter test

## What I did today

- Set up a JMeter CRUD test with mix GET 70% / POST 10% / PUT 13% / DELETE 7%.
- Wired CSV data (ids_all, ids_user1, posts) and fixed URL/variable issues for DELETE/PUT.
- Drove load with Constant Throughput Timer at 700 → 1000 → 1400 → 2000 rpm and analyzed steady-state from .jtl.

---

## What I learned

- Use Transaction Controller (parent sample) as the main SLA line; drill into child labels for root cause.
- CTT under the Transaction Controller cleanly caps total CRUD RPS for the group.
- At high load (2000 rpm) PUT becomes the bottleneck (write contention/locks) even if Error% stays 0.
  

  ### Key results (steady-state)
  
  700 rpm ~25 rps, P95 ≈ 160 ms (stable)
  
  1000 rpm ~36–37 rps, P95 ≈ 300–400 ms (stable)
  
  1400 rpm ~53–54 rps, P95 ≈ 120–200 ms (best stable ceiling)
  
  2000 rpm ~66 rps, PUT latency spikes to seconds

---

## Reflections

- Separating reads from writes (or capping write RPS) will likely protect user-facing latencies under peak conditions.
- Keeping DELETE low and validating via steady-state trimming makes results clean and comparable.

---

## Goals for tomorrow

- Add/verify DB index for UPDATE ... WHERE id AND user_id, reduce write contention.
- Re-run A/B at 1400 & 2000 rpm (10 min each) and compare Error%, P95/P99, Throughput.
