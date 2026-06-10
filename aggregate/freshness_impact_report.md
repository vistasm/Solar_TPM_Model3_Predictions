# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-06-10 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (100.0%) is 100.0% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (2.8%) is 2.6× the overall rate (1.1%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   36 |   13.0 | 11.1% | 0.454 | 0.1 |       34 | 100.0% |  17.6% | 2.0× | 0.0% |   0.5000 |
|       OK |   22 |   36.9 | 4.5% | 0.407 | 0.1 |       21 | 100.0% |  33.3% | 7.0× | 0.0% |   0.1429 |
| DEGRADED |   34 |  118.1 | 11.8% | 0.396 | 0.1 |       33 | 0.0% |   0.0% |    - | 16.7% |   0.2727 |
|      ALL |   92 |   57.5 | 9.8% | 0.421 | 0.1 |       88 | 50.0% |  13.8% | 1.5× | 6.8% |   0.3295 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   36 |   13.0 | 2.8% | 0.437 | 0.0 |       34 | 100.0% |  20.0% | 6.8× | 0.0% |   0.1471 |
|       OK |   22 |   36.9 | 0.0% | 0.335 | 0.0 |       21 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   34 |  118.1 | 0.0% | 0.320 | 0.0 |       33 |    - |   0.0% |    - | 0.0% |   0.0909 |
|      ALL |   92 |   57.5 | 1.1% | 0.370 | 0.0 |       88 | 100.0% |  12.5% | 11.0× | 0.0% |   0.0909 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   36 |   13.0 | 2.8% | 0.258 | 0.0 |       34 | 0.0% |   0.0% |    - | 3.2% |   0.0882 |
|       OK |   22 |   36.9 | 9.1% | 0.323 | 0.1 |       21 | 0.0% |      - |    - | 9.5% |   0.0000 |
| DEGRADED |   34 |  118.1 | 5.9% | 0.262 | 0.1 |       33 | 0.0% |   0.0% |    - | 3.1% |   0.0303 |
|      ALL |   92 |   57.5 | 5.4% | 0.275 | 0.1 |       88 | 0.0% |   0.0% |    - | 4.8% |   0.0455 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   14.3 | 9.1% | 0.406 | 0.1 |        9 |    - |   0.0% |    - | 0.0% |   0.3333 |
|       OK |    8 |   39.2 | 0.0% | 0.395 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   12 |   89.3 | 16.7% | 0.447 | 0.2 |       11 | 0.0% |   0.0% |    - | 28.6% |   0.3636 |
|      ALL |   31 |   49.8 | 9.7% | 0.419 | 0.1 |       27 | 0.0% |   0.0% |    - | 10.0% |   0.2593 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   14.3 | 0.0% | 0.386 | 0.0 |        9 |    - |   0.0% |    - | 0.0% |   0.1111 |
|       OK |    8 |   39.2 | 0.0% | 0.294 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   12 |   89.3 | 0.0% | 0.335 | 0.0 |       11 |    - |   0.0% |    - | 0.0% |   0.0909 |
|      ALL |   31 |   49.8 | 0.0% | 0.343 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   14.3 | 0.0% | 0.269 | 0.0 |        9 |    - |   0.0% |    - | 0.0% |   0.1111 |
|       OK |    8 |   39.2 | 12.5% | 0.338 | 0.1 |        7 | 0.0% |      - |    - | 14.3% |   0.0000 |
| DEGRADED |   12 |   89.3 | 8.3% | 0.339 | 0.1 |       11 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   49.8 | 6.5% | 0.314 | 0.1 |       27 | 0.0% |   0.0% |    - | 3.9% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available