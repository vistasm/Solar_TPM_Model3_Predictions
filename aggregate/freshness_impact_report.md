# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-06-24 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (75.0%) is 75.0% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (2.4%) is 2.5× the overall rate (0.9%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   42 |   12.9 | 9.5% | 0.445 | 0.1 |       40 | 75.0% |  16.7% | 1.7× | 4.5% |   0.4500 |
|       OK |   25 |   37.2 | 4.0% | 0.396 | 0.0 |       24 | 100.0% |  33.3% | 8.0× | 0.0% |   0.1250 |
| DEGRADED |   39 |  114.7 | 10.3% | 0.390 | 0.1 |       38 | 0.0% |   0.0% |    - | 14.3% |   0.2632 |
|      ALL |  106 |   56.1 | 8.5% | 0.413 | 0.1 |      102 | 44.4% |  12.9% | 1.5× | 7.0% |   0.3039 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   42 |   12.9 | 2.4% | 0.426 | 0.0 |       40 | 100.0% |  20.0% | 8.0× | 0.0% |   0.1250 |
|       OK |   25 |   37.2 | 0.0% | 0.323 | 0.0 |       24 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   39 |  114.7 | 0.0% | 0.314 | 0.0 |       38 |    - |   0.0% |    - | 0.0% |   0.0789 |
|      ALL |  106 |   56.1 | 0.9% | 0.361 | 0.0 |      102 | 100.0% |  12.5% | 12.8× | 0.0% |   0.0784 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   42 |   12.9 | 4.8% | 0.284 | 0.1 |       40 | 0.0% |   0.0% |    - | 5.4% |   0.0750 |
|       OK |   25 |   37.2 | 8.0% | 0.305 | 0.1 |       24 | 0.0% |      - |    - | 8.3% |   0.0000 |
| DEGRADED |   39 |  114.7 | 5.1% | 0.271 | 0.1 |       38 | 0.0% |   0.0% |    - | 5.4% |   0.0263 |
|      ALL |  106 |   56.1 | 5.7% | 0.284 | 0.1 |      102 | 0.0% |   0.0% |    - | 6.1% |   0.0392 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   12.9 | 8.3% | 0.420 | 0.1 |       10 | 0.0% |   0.0% |    - | 14.3% |   0.3000 |
|       OK |    6 |   41.2 | 0.0% | 0.402 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |   97.1 | 15.4% | 0.427 | 0.1 |       12 | 0.0% |   0.0% |    - | 25.0% |   0.3333 |
|      ALL |   31 |   53.7 | 9.7% | 0.419 | 0.1 |       27 | 0.0% |   0.0% |    - | 15.0% |   0.2593 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   12.9 | 0.0% | 0.417 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.1000 |
|       OK |    6 |   41.2 | 0.0% | 0.295 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |   97.1 | 0.0% | 0.335 | 0.0 |       12 |    - |   0.0% |    - | 0.0% |   0.0833 |
|      ALL |   31 |   53.7 | 0.0% | 0.359 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   12.9 | 8.3% | 0.381 | 0.1 |       10 | 0.0% |   0.0% |    - | 11.1% |   0.1000 |
|       OK |    6 |   41.2 | 16.7% | 0.382 | 0.2 |        5 | 0.0% |      - |    - | 20.0% |   0.0000 |
| DEGRADED |   13 |   97.1 | 7.7% | 0.372 | 0.1 |       12 | 0.0% |      - |    - | 8.3% |   0.0000 |
|      ALL |   31 |   53.7 | 9.7% | 0.378 | 0.1 |       27 | 0.0% |   0.0% |    - | 11.5% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available