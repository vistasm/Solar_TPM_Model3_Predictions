# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-05-20 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (100.0%) is 100.0% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (3.5%) is 2.4× the overall rate (1.4%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   29 |   12.6 | 10.3% | 0.460 | 0.1 |       27 | 100.0% |  20.0% | 1.8× | 0.0% |   0.5556 |
|       OK |   17 |   35.1 | 5.9% | 0.394 | 0.1 |       16 | 100.0% |  33.3% | 5.3× | 0.0% |   0.1875 |
| DEGRADED |   25 |  125.7 | 8.0% | 0.368 | 0.1 |       24 | 0.0% |   0.0% |    - | 10.5% |   0.2083 |
|      ALL |   71 |   57.8 | 8.5% | 0.411 | 0.1 |       67 | 66.7% |  17.4% | 1.9× | 4.5% |   0.3433 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   29 |   12.6 | 3.5% | 0.439 | 0.0 |       27 | 100.0% |  25.0% | 6.8× | 0.0% |   0.1481 |
|       OK |   17 |   35.1 | 0.0% | 0.336 | 0.0 |       16 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   25 |  125.7 | 0.0% | 0.304 | 0.0 |       24 |    - |   0.0% |    - | 0.0% |   0.0833 |
|      ALL |   71 |   57.8 | 1.4% | 0.367 | 0.0 |       67 | 100.0% |  16.7% | 11.2× | 0.0% |   0.0896 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   29 |   12.6 | 3.5% | 0.251 | 0.0 |       27 | 0.0% |   0.0% |    - | 4.0% |   0.0741 |
|       OK |   17 |   35.1 | 5.9% | 0.273 | 0.1 |       16 | 0.0% |      - |    - | 6.2% |   0.0000 |
| DEGRADED |   25 |  125.7 | 4.0% | 0.212 | 0.0 |       24 | 0.0% |   0.0% |    - | 4.3% |   0.0417 |
|      ALL |   71 |   57.8 | 4.2% | 0.242 | 0.0 |       67 | 0.0% |   0.0% |    - | 4.7% |   0.0448 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   11.4 | 23.1% | 0.533 | 0.2 |       11 | 100.0% |  42.9% | 1.6× | 0.0% |   0.6364 |
|       OK |    6 |   34.2 | 0.0% | 0.313 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   11 |  131.3 | 0.0% | 0.370 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.4000 |
|      ALL |   30 |   59.9 | 10.0% | 0.429 | 0.1 |       26 | 100.0% |  27.3% | 2.4× | 0.0% |   0.4231 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   11.4 | 7.7% | 0.519 | 0.1 |       11 | 100.0% |  50.0% | 5.5× | 0.0% |   0.1818 |
|       OK |    6 |   34.2 | 0.0% | 0.242 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   11 |  131.3 | 0.0% | 0.298 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.2000 |
|      ALL |   30 |   59.9 | 3.3% | 0.383 | 0.0 |       26 | 100.0% |  25.0% | 6.5× | 0.0% |   0.1538 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   11.4 | 0.0% | 0.274 | 0.0 |       11 |    - |   0.0% |    - | 0.0% |   0.0909 |
|       OK |    6 |   34.2 | 0.0% | 0.118 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   11 |  131.3 | 0.0% | 0.178 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.1000 |
|      ALL |   30 |   59.9 | 0.0% | 0.207 | 0.0 |       26 |    - |   0.0% |    - | 0.0% |   0.0769 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available