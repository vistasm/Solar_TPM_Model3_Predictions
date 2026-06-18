# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-06-18 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (75.0%) is 75.0% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (2.6%) is 2.6× the overall rate (1.0%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   39 |   13.1 | 10.3% | 0.451 | 0.1 |       39 | 75.0% |  17.6% | 1.7× | 4.5% |   0.4359 |
|       OK |   24 |   37.4 | 4.2% | 0.389 | 0.0 |       23 | 100.0% |  33.3% | 7.7× | 0.0% |   0.1304 |
| DEGRADED |   37 |  115.7 | 10.8% | 0.394 | 0.1 |       34 | 0.0% |   0.0% |    - | 16.0% |   0.2647 |
|      ALL |  100 |   56.9 | 9.0% | 0.415 | 0.1 |       96 | 44.4% |  13.8% | 1.5× | 7.5% |   0.3021 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   39 |   13.1 | 2.6% | 0.438 | 0.0 |       39 | 100.0% |  20.0% | 7.8× | 0.0% |   0.1282 |
|       OK |   24 |   37.4 | 0.0% | 0.321 | 0.0 |       23 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   37 |  115.7 | 0.0% | 0.320 | 0.0 |       34 |    - |   0.0% |    - | 0.0% |   0.0882 |
|      ALL |  100 |   56.9 | 1.0% | 0.366 | 0.0 |       96 | 100.0% |  12.5% | 12.0× | 0.0% |   0.0833 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   39 |   13.1 | 5.1% | 0.276 | 0.1 |       39 | 0.0% |   0.0% |    - | 5.6% |   0.0769 |
|       OK |   24 |   37.4 | 8.3% | 0.307 | 0.1 |       23 | 0.0% |      - |    - | 8.7% |   0.0000 |
| DEGRADED |   37 |  115.7 | 5.4% | 0.281 | 0.1 |       34 | 0.0% |   0.0% |    - | 6.1% |   0.0294 |
|      ALL |  100 |   56.9 | 6.0% | 0.285 | 0.1 |       96 | 0.0% |   0.0% |    - | 6.5% |   0.0417 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   15.0 | 9.1% | 0.399 | 0.1 |       11 | 0.0% |   0.0% |    - | 11.1% |   0.1818 |
|       OK |    7 |   42.8 | 0.0% | 0.377 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |   91.2 | 15.4% | 0.434 | 0.1 |       10 | 0.0% |   0.0% |    - | 33.3% |   0.4000 |
|      ALL |   31 |   53.2 | 9.7% | 0.409 | 0.1 |       27 | 0.0% |   0.0% |    - | 14.3% |   0.2222 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   15.0 | 0.0% | 0.401 | 0.0 |       11 |    - |   0.0% |    - | 0.0% |   0.0909 |
|       OK |    7 |   42.8 | 0.0% | 0.285 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |   91.2 | 0.0% | 0.335 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.1000 |
|      ALL |   31 |   53.2 | 0.0% | 0.347 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   15.0 | 9.1% | 0.319 | 0.1 |       11 | 0.0% |   0.0% |    - | 10.0% |   0.0909 |
|       OK |    7 |   42.8 | 14.3% | 0.391 | 0.1 |        6 | 0.0% |      - |    - | 16.7% |   0.0000 |
| DEGRADED |   13 |   91.2 | 7.7% | 0.398 | 0.1 |       10 | 0.0% |      - |    - | 10.0% |   0.0000 |
|      ALL |   31 |   53.2 | 9.7% | 0.368 | 0.1 |       27 | 0.0% |   0.0% |    - | 11.5% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available