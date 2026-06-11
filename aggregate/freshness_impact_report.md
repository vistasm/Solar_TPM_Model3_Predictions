# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-06-11 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (100.0%) is 100.0% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (2.7%) is 2.5× the overall rate (1.1%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   37 |   12.8 | 10.8% | 0.458 | 0.1 |       35 | 100.0% |  17.6% | 2.1× | 0.0% |   0.4857 |
|       OK |   22 |   36.9 | 4.5% | 0.407 | 0.1 |       21 | 100.0% |  33.3% | 7.0× | 0.0% |   0.1429 |
| DEGRADED |   34 |  118.1 | 11.8% | 0.396 | 0.1 |       33 | 0.0% |   0.0% |    - | 16.7% |   0.2727 |
|      ALL |   93 |   57.0 | 9.7% | 0.423 | 0.1 |       89 | 50.0% |  13.8% | 1.5× | 6.7% |   0.3258 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   37 |   12.8 | 2.7% | 0.442 | 0.0 |       35 | 100.0% |  20.0% | 7.0× | 0.0% |   0.1429 |
|       OK |   22 |   36.9 | 0.0% | 0.335 | 0.0 |       21 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   34 |  118.1 | 0.0% | 0.320 | 0.0 |       33 |    - |   0.0% |    - | 0.0% |   0.0909 |
|      ALL |   93 |   57.0 | 1.1% | 0.372 | 0.0 |       89 | 100.0% |  12.5% | 11.1× | 0.0% |   0.0899 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   37 |   12.8 | 5.4% | 0.277 | 0.1 |       35 | 0.0% |   0.0% |    - | 3.1% |   0.0857 |
|       OK |   22 |   36.9 | 9.1% | 0.323 | 0.1 |       21 | 0.0% |      - |    - | 9.5% |   0.0000 |
| DEGRADED |   34 |  118.1 | 5.9% | 0.262 | 0.1 |       33 | 0.0% |   0.0% |    - | 3.1% |   0.0303 |
|      ALL |   93 |   57.0 | 6.5% | 0.282 | 0.1 |       89 | 0.0% |   0.0% |    - | 4.7% |   0.0449 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   13.4 | 9.1% | 0.412 | 0.1 |        9 |    - |   0.0% |    - | 0.0% |   0.3333 |
|       OK |    8 |   39.2 | 0.0% | 0.395 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   12 |   89.3 | 16.7% | 0.447 | 0.2 |       11 | 0.0% |   0.0% |    - | 28.6% |   0.3636 |
|      ALL |   31 |   49.4 | 9.7% | 0.421 | 0.1 |       27 | 0.0% |   0.0% |    - | 10.0% |   0.2593 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   13.4 | 0.0% | 0.388 | 0.0 |        9 |    - |   0.0% |    - | 0.0% |   0.1111 |
|       OK |    8 |   39.2 | 0.0% | 0.294 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   12 |   89.3 | 0.0% | 0.335 | 0.0 |       11 |    - |   0.0% |    - | 0.0% |   0.0909 |
|      ALL |   31 |   49.4 | 0.0% | 0.343 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   13.4 | 9.1% | 0.328 | 0.1 |        9 |    - |   0.0% |    - | 0.0% |   0.1111 |
|       OK |    8 |   39.2 | 12.5% | 0.338 | 0.1 |        7 | 0.0% |      - |    - | 14.3% |   0.0000 |
| DEGRADED |   12 |   89.3 | 8.3% | 0.339 | 0.1 |       11 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   49.4 | 9.7% | 0.335 | 0.1 |       27 | 0.0% |   0.0% |    - | 3.9% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available