# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-06-14 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (75.0%) is 75.0% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (2.6%) is 2.5× the overall rate (1.0%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   39 |   13.1 | 10.3% | 0.451 | 0.1 |       36 | 75.0% |  17.6% | 1.6× | 5.3% |   0.4722 |
|       OK |   23 |   37.2 | 4.3% | 0.398 | 0.0 |       22 | 100.0% |  33.3% | 7.3× | 0.0% |   0.1364 |
| DEGRADED |   34 |  118.1 | 11.8% | 0.396 | 0.1 |       34 | 0.0% |   0.0% |    - | 16.0% |   0.2647 |
|      ALL |   96 |   56.1 | 9.4% | 0.419 | 0.1 |       92 | 44.4% |  13.8% | 1.4× | 7.9% |   0.3152 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   39 |   13.1 | 2.6% | 0.438 | 0.0 |       36 | 100.0% |  20.0% | 7.2× | 0.0% |   0.1389 |
|       OK |   23 |   37.2 | 0.0% | 0.329 | 0.0 |       22 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   34 |  118.1 | 0.0% | 0.320 | 0.0 |       34 |    - |   0.0% |    - | 0.0% |   0.0882 |
|      ALL |   96 |   56.1 | 1.0% | 0.370 | 0.0 |       92 | 100.0% |  12.5% | 11.5× | 0.0% |   0.0870 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   39 |   13.1 | 5.1% | 0.276 | 0.1 |       36 | 0.0% |   0.0% |    - | 3.0% |   0.0833 |
|       OK |   23 |   37.2 | 8.7% | 0.315 | 0.1 |       22 | 0.0% |      - |    - | 9.1% |   0.0000 |
| DEGRADED |   34 |  118.1 | 5.9% | 0.262 | 0.1 |       34 | 0.0% |   0.0% |    - | 6.1% |   0.0294 |
|      ALL |   96 |   56.1 | 6.2% | 0.280 | 0.1 |       92 | 0.0% |   0.0% |    - | 5.7% |   0.0435 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   14.2 | 7.7% | 0.397 | 0.1 |       10 | 0.0% |   0.0% |    - | 14.3% |   0.3000 |
|       OK |    8 |   39.8 | 0.0% | 0.360 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   10 |   92.0 | 20.0% | 0.456 | 0.2 |       10 | 0.0% |   0.0% |    - | 33.3% |   0.4000 |
|      ALL |   31 |   45.9 | 9.7% | 0.406 | 0.1 |       27 | 0.0% |   0.0% |    - | 15.0% |   0.2593 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   14.2 | 0.0% | 0.383 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.1000 |
|       OK |    8 |   39.8 | 0.0% | 0.264 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   10 |   92.0 | 0.0% | 0.341 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.1000 |
|      ALL |   31 |   45.9 | 0.0% | 0.339 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   14.2 | 7.7% | 0.317 | 0.1 |       10 |    - |   0.0% |    - | 0.0% |   0.1000 |
|       OK |    8 |   39.8 | 12.5% | 0.335 | 0.1 |        7 | 0.0% |      - |    - | 14.3% |   0.0000 |
| DEGRADED |   10 |   92.0 | 10.0% | 0.369 | 0.1 |       10 | 0.0% |      - |    - | 10.0% |   0.0000 |
|      ALL |   31 |   45.9 | 9.7% | 0.339 | 0.1 |       27 | 0.0% |   0.0% |    - | 7.7% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available