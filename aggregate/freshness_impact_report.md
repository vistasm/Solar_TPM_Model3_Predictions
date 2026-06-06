# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-06-06 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (100.0%) is 100.0% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (2.9%) is 2.6× the overall rate (1.1%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   34 |   13.0 | 8.8% | 0.447 | 0.1 |       31 | 100.0% |  20.0% | 2.1× | 0.0% |   0.4839 |
|       OK |   21 |   36.8 | 4.8% | 0.406 | 0.1 |       20 | 100.0% |  33.3% | 6.7× | 0.0% |   0.1500 |
| DEGRADED |   33 |  119.7 | 12.1% | 0.385 | 0.1 |       33 | 0.0% |   0.0% |    - | 16.7% |   0.2727 |
|      ALL |   88 |   58.7 | 9.1% | 0.414 | 0.1 |       84 | 50.0% |  14.8% | 1.6× | 7.0% |   0.3214 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   34 |   13.0 | 2.9% | 0.427 | 0.0 |       31 | 100.0% |  25.0% | 7.8× | 0.0% |   0.1290 |
|       OK |   21 |   36.8 | 0.0% | 0.334 | 0.0 |       20 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   33 |  119.7 | 0.0% | 0.310 | 0.0 |       33 |    - |   0.0% |    - | 0.0% |   0.0909 |
|      ALL |   88 |   58.7 | 1.1% | 0.361 | 0.0 |       84 | 100.0% |  14.3% | 12.0× | 0.0% |   0.0833 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   34 |   13.0 | 2.9% | 0.247 | 0.0 |       31 | 0.0% |   0.0% |    - | 3.5% |   0.0645 |
|       OK |   21 |   36.8 | 9.5% | 0.326 | 0.1 |       20 | 0.0% |      - |    - | 5.0% |   0.0000 |
| DEGRADED |   33 |  119.7 | 3.0% | 0.240 | 0.0 |       33 | 0.0% |   0.0% |    - | 3.1% |   0.0303 |
|      ALL |   88 |   58.7 | 4.5% | 0.263 | 0.1 |       84 | 0.0% |   0.0% |    - | 3.7% |   0.0357 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   14.6 | 0.0% | 0.355 | 0.0 |        7 |    - |   0.0% |    - | 0.0% |   0.1429 |
|       OK |    8 |   39.0 | 0.0% | 0.368 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |   88.2 | 15.4% | 0.402 | 0.1 |       13 | 0.0% |   0.0% |    - | 28.6% |   0.4615 |
|      ALL |   31 |   51.8 | 6.5% | 0.378 | 0.1 |       27 | 0.0% |   0.0% |    - | 10.0% |   0.2593 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   14.6 | 0.0% | 0.319 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    8 |   39.0 | 0.0% | 0.271 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |   88.2 | 0.0% | 0.301 | 0.0 |       13 |    - |   0.0% |    - | 0.0% |   0.1538 |
|      ALL |   31 |   51.8 | 0.0% | 0.299 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   14.6 | 0.0% | 0.211 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    8 |   39.0 | 12.5% | 0.312 | 0.1 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |   88.2 | 0.0% | 0.269 | 0.0 |       13 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   51.8 | 3.2% | 0.261 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available