# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-06-27 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (75.0%) is 75.0% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (2.4%) is 2.6× the overall rate (0.9%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   42 |   12.9 | 9.5% | 0.445 | 0.1 |       42 | 75.0% |  15.8% | 1.7× | 4.3% |   0.4524 |
|       OK |   25 |   37.2 | 4.0% | 0.396 | 0.0 |       25 | 100.0% |  33.3% | 8.3× | 0.0% |   0.1200 |
| DEGRADED |   42 |  114.1 | 11.9% | 0.416 | 0.1 |       38 | 0.0% |   0.0% |    - | 14.3% |   0.2632 |
|      ALL |  109 |   57.5 | 9.2% | 0.422 | 0.1 |      105 | 44.4% |  12.5% | 1.5× | 6.9% |   0.3048 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   42 |   12.9 | 2.4% | 0.426 | 0.0 |       42 | 100.0% |  16.7% | 7.0× | 0.0% |   0.1429 |
|       OK |   25 |   37.2 | 0.0% | 0.323 | 0.0 |       25 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   42 |  114.1 | 0.0% | 0.341 | 0.0 |       38 |    - |   0.0% |    - | 0.0% |   0.0789 |
|      ALL |  109 |   57.5 | 0.9% | 0.369 | 0.0 |      105 | 100.0% |  11.1% | 11.7× | 0.0% |   0.0857 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   42 |   12.9 | 4.8% | 0.284 | 0.1 |       42 | 0.0% |   0.0% |    - | 5.1% |   0.0714 |
|       OK |   25 |   37.2 | 8.0% | 0.305 | 0.1 |       25 | 0.0% |      - |    - | 8.0% |   0.0000 |
| DEGRADED |   42 |  114.1 | 7.1% | 0.309 | 0.1 |       38 | 0.0% |   0.0% |    - | 5.4% |   0.0263 |
|      ALL |  109 |   57.5 | 6.4% | 0.299 | 0.1 |      105 | 0.0% |   0.0% |    - | 5.9% |   0.0381 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   12.9 | 8.3% | 0.420 | 0.1 |       12 | 0.0% |   0.0% |    - | 12.5% |   0.3333 |
|       OK |    6 |   41.2 | 0.0% | 0.402 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |  100.6 | 15.4% | 0.488 | 0.1 |        9 | 0.0% |   0.0% |    - | 20.0% |   0.4444 |
|      ALL |   31 |   55.2 | 9.7% | 0.445 | 0.1 |       27 | 0.0% |   0.0% |    - | 10.5% |   0.2963 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   12.9 | 0.0% | 0.417 | 0.0 |       12 |    - |   0.0% |    - | 0.0% |   0.1667 |
|       OK |    6 |   41.2 | 0.0% | 0.295 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |  100.6 | 0.0% | 0.412 | 0.0 |        9 |    - |   0.0% |    - | 0.0% |   0.1111 |
|      ALL |   31 |   55.2 | 0.0% | 0.391 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.1111 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   12.9 | 8.3% | 0.381 | 0.1 |       12 | 0.0% |   0.0% |    - | 9.1% |   0.0833 |
|       OK |    6 |   41.2 | 16.7% | 0.382 | 0.2 |        6 | 0.0% |      - |    - | 16.7% |   0.0000 |
| DEGRADED |   13 |  100.6 | 15.4% | 0.491 | 0.1 |        9 | 0.0% |      - |    - | 11.1% |   0.0000 |
|      ALL |   31 |   55.2 | 12.9% | 0.427 | 0.1 |       27 | 0.0% |   0.0% |    - | 11.5% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available