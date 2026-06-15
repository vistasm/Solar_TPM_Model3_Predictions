# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-06-15 UTC
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
|    FRESH |   39 |   13.1 | 10.3% | 0.451 | 0.1 |       37 | 75.0% |  17.6% | 1.6× | 5.0% |   0.4595 |
|       OK |   24 |   37.4 | 4.2% | 0.389 | 0.0 |       22 | 100.0% |  33.3% | 7.3× | 0.0% |   0.1364 |
| DEGRADED |   34 |  118.1 | 11.8% | 0.396 | 0.1 |       34 | 0.0% |   0.0% |    - | 16.0% |   0.2647 |
|      ALL |   97 |   55.9 | 9.3% | 0.416 | 0.1 |       93 | 44.4% |  13.8% | 1.4× | 7.8% |   0.3118 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   39 |   13.1 | 2.6% | 0.438 | 0.0 |       37 | 100.0% |  20.0% | 7.4× | 0.0% |   0.1351 |
|       OK |   24 |   37.4 | 0.0% | 0.321 | 0.0 |       22 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   34 |  118.1 | 0.0% | 0.320 | 0.0 |       34 |    - |   0.0% |    - | 0.0% |   0.0882 |
|      ALL |   97 |   55.9 | 1.0% | 0.368 | 0.0 |       93 | 100.0% |  12.5% | 11.6× | 0.0% |   0.0860 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   39 |   13.1 | 5.1% | 0.276 | 0.1 |       37 | 0.0% |   0.0% |    - | 5.9% |   0.0811 |
|       OK |   24 |   37.4 | 8.3% | 0.307 | 0.1 |       22 | 0.0% |      - |    - | 9.1% |   0.0000 |
| DEGRADED |   34 |  118.1 | 5.9% | 0.262 | 0.1 |       34 | 0.0% |   0.0% |    - | 6.1% |   0.0294 |
|      ALL |   97 |   55.9 | 6.2% | 0.279 | 0.1 |       93 | 0.0% |   0.0% |    - | 6.7% |   0.0430 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   14.2 | 7.7% | 0.397 | 0.1 |       11 | 0.0% |   0.0% |    - | 12.5% |   0.2727 |
|       OK |    8 |   40.7 | 0.0% | 0.355 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   10 |   92.0 | 20.0% | 0.456 | 0.2 |       10 | 0.0% |   0.0% |    - | 33.3% |   0.4000 |
|      ALL |   31 |   46.1 | 9.7% | 0.405 | 0.1 |       27 | 0.0% |   0.0% |    - | 15.0% |   0.2593 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   14.2 | 0.0% | 0.383 | 0.0 |       11 |    - |   0.0% |    - | 0.0% |   0.0909 |
|       OK |    8 |   40.7 | 0.0% | 0.259 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   10 |   92.0 | 0.0% | 0.341 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.1000 |
|      ALL |   31 |   46.1 | 0.0% | 0.338 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   14.2 | 7.7% | 0.317 | 0.1 |       11 | 0.0% |   0.0% |    - | 10.0% |   0.0909 |
|       OK |    8 |   40.7 | 12.5% | 0.347 | 0.1 |        6 | 0.0% |      - |    - | 16.7% |   0.0000 |
| DEGRADED |   10 |   92.0 | 10.0% | 0.369 | 0.1 |       10 | 0.0% |      - |    - | 10.0% |   0.0000 |
|      ALL |   31 |   46.1 | 9.7% | 0.342 | 0.1 |       27 | 0.0% |   0.0% |    - | 11.5% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available