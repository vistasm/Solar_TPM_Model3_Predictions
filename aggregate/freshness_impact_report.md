# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-06-12 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (100.0%) is 100.0% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (2.6%) is 2.5× the overall rate (1.1%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   38 |   13.0 | 10.5% | 0.457 | 0.1 |       35 | 100.0% |  17.6% | 2.1× | 0.0% |   0.4857 |
|       OK |   22 |   36.9 | 4.5% | 0.407 | 0.1 |       22 | 100.0% |  33.3% | 7.3× | 0.0% |   0.1364 |
| DEGRADED |   34 |  118.1 | 11.8% | 0.396 | 0.1 |       33 | 0.0% |   0.0% |    - | 16.7% |   0.2727 |
|      ALL |   94 |   56.6 | 9.6% | 0.423 | 0.1 |       90 | 50.0% |  13.8% | 1.6× | 6.6% |   0.3222 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   38 |   13.0 | 2.6% | 0.443 | 0.0 |       35 | 100.0% |  20.0% | 7.0× | 0.0% |   0.1429 |
|       OK |   22 |   36.9 | 0.0% | 0.335 | 0.0 |       22 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   34 |  118.1 | 0.0% | 0.320 | 0.0 |       33 |    - |   0.0% |    - | 0.0% |   0.0909 |
|      ALL |   94 |   56.6 | 1.1% | 0.373 | 0.0 |       90 | 100.0% |  12.5% | 11.2× | 0.0% |   0.0889 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   38 |   13.0 | 5.3% | 0.279 | 0.1 |       35 | 0.0% |   0.0% |    - | 3.1% |   0.0857 |
|       OK |   22 |   36.9 | 9.1% | 0.323 | 0.1 |       22 | 0.0% |      - |    - | 9.1% |   0.0000 |
| DEGRADED |   34 |  118.1 | 5.9% | 0.262 | 0.1 |       33 | 0.0% |   0.0% |    - | 3.1% |   0.0303 |
|      ALL |   94 |   56.6 | 6.4% | 0.283 | 0.1 |       90 | 0.0% |   0.0% |    - | 4.7% |   0.0444 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   14.0 | 8.3% | 0.413 | 0.1 |        9 |    - |   0.0% |    - | 0.0% |   0.3333 |
|       OK |    7 |   39.1 | 0.0% | 0.381 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   12 |   89.3 | 16.7% | 0.447 | 0.2 |       11 | 0.0% |   0.0% |    - | 28.6% |   0.3636 |
|      ALL |   31 |   48.8 | 9.7% | 0.419 | 0.1 |       27 | 0.0% |   0.0% |    - | 10.0% |   0.2593 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   14.0 | 0.0% | 0.397 | 0.0 |        9 |    - |   0.0% |    - | 0.0% |   0.1111 |
|       OK |    7 |   39.1 | 0.0% | 0.273 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   12 |   89.3 | 0.0% | 0.335 | 0.0 |       11 |    - |   0.0% |    - | 0.0% |   0.0909 |
|      ALL |   31 |   48.8 | 0.0% | 0.345 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   14.0 | 8.3% | 0.330 | 0.1 |        9 |    - |   0.0% |    - | 0.0% |   0.1111 |
|       OK |    7 |   39.1 | 14.3% | 0.364 | 0.1 |        7 | 0.0% |      - |    - | 14.3% |   0.0000 |
| DEGRADED |   12 |   89.3 | 8.3% | 0.339 | 0.1 |       11 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   48.8 | 9.7% | 0.341 | 0.1 |       27 | 0.0% |   0.0% |    - | 3.9% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available