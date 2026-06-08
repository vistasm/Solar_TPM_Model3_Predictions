# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-06-08 UTC
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
|    FRESH |   35 |   13.1 | 8.6% | 0.446 | 0.1 |       33 | 100.0% |  18.8% | 2.1× | 0.0% |   0.4848 |
|       OK |   22 |   36.9 | 4.5% | 0.407 | 0.1 |       20 | 100.0% |  33.3% | 6.7× | 0.0% |   0.1500 |
| DEGRADED |   33 |  119.7 | 12.1% | 0.385 | 0.1 |       33 | 0.0% |   0.0% |    - | 16.7% |   0.2727 |
|      ALL |   90 |   58.0 | 8.9% | 0.414 | 0.1 |       86 | 50.0% |  14.3% | 1.5× | 6.9% |   0.3256 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   35 |   13.1 | 2.9% | 0.428 | 0.0 |       33 | 100.0% |  20.0% | 6.6× | 0.0% |   0.1515 |
|       OK |   22 |   36.9 | 0.0% | 0.335 | 0.0 |       20 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   33 |  119.7 | 0.0% | 0.310 | 0.0 |       33 |    - |   0.0% |    - | 0.0% |   0.0909 |
|      ALL |   90 |   58.0 | 1.1% | 0.362 | 0.0 |       86 | 100.0% |  12.5% | 10.8× | 0.0% |   0.0930 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   35 |   13.1 | 2.9% | 0.246 | 0.0 |       33 | 0.0% |   0.0% |    - | 3.3% |   0.0909 |
|       OK |   22 |   36.9 | 9.1% | 0.323 | 0.1 |       20 | 0.0% |      - |    - | 5.0% |   0.0000 |
| DEGRADED |   33 |  119.7 | 3.0% | 0.240 | 0.0 |       33 | 0.0% |   0.0% |    - | 3.1% |   0.0303 |
|      ALL |   90 |   58.0 | 4.4% | 0.263 | 0.0 |       86 | 0.0% |   0.0% |    - | 3.7% |   0.0465 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   14.7 | 0.0% | 0.375 | 0.0 |        8 |    - |   0.0% |    - | 0.0% |   0.2500 |
|       OK |    9 |   39.1 | 0.0% | 0.374 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   12 |   89.2 | 16.7% | 0.419 | 0.2 |       12 | 0.0% |   0.0% |    - | 28.6% |   0.4167 |
|      ALL |   31 |   50.6 | 6.5% | 0.392 | 0.1 |       27 | 0.0% |   0.0% |    - | 10.0% |   0.2593 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   14.7 | 0.0% | 0.347 | 0.0 |        8 |    - |   0.0% |    - | 0.0% |   0.1250 |
|       OK |    9 |   39.1 | 0.0% | 0.282 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   12 |   89.2 | 0.0% | 0.317 | 0.0 |       12 |    - |   0.0% |    - | 0.0% |   0.1667 |
|      ALL |   31 |   50.6 | 0.0% | 0.316 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.1111 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   14.7 | 0.0% | 0.227 | 0.0 |        8 |    - |   0.0% |    - | 0.0% |   0.1250 |
|       OK |    9 |   39.1 | 11.1% | 0.307 | 0.1 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   12 |   89.2 | 0.0% | 0.289 | 0.0 |       12 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   50.6 | 3.2% | 0.274 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available