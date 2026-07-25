# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-07-25 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (80.0%) is 80.0% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (11.7%) is 2.3× the overall rate (5.1%) — score distribution shift detected
🟢 **X+**: FRESH precision (16.7%) is 16.7% HIGHER than DEGRADED (0.0%) — fresher data is helping

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   60 |   12.4 | 18.3% | 0.513 | 0.2 |       57 | 80.0% |  28.6% | 1.6× | 6.9% |   0.4912 |
|       OK |   29 |   37.2 | 3.5% | 0.389 | 0.0 |       28 | 100.0% |  25.0% | 7.0× | 0.0% |   0.1429 |
| DEGRADED |   48 |  115.2 | 10.4% | 0.411 | 0.1 |       48 | 0.0% |   0.0% |    - | 13.9% |   0.2500 |
|      ALL |  137 |   53.6 | 12.4% | 0.451 | 0.1 |      133 | 56.2% |  20.4% | 1.7× | 7.9% |   0.3308 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   60 |   12.4 | 11.7% | 0.500 | 0.1 |       57 | 66.7% |  36.4% | 3.5× | 4.3% |   0.1930 |
|       OK |   29 |   37.2 | 0.0% | 0.318 | 0.0 |       28 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   48 |  115.2 | 0.0% | 0.334 | 0.0 |       48 |    - |   0.0% |    - | 0.0% |   0.0625 |
|      ALL |  137 |   53.6 | 5.1% | 0.403 | 0.1 |      133 | 66.7% |  28.6% | 6.3× | 1.7% |   0.1053 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   60 |   12.4 | 10.0% | 0.360 | 0.1 |       57 | 16.7% |  20.0% | 1.9× | 9.6% |   0.0877 |
|       OK |   29 |   37.2 | 6.9% | 0.300 | 0.1 |       28 | 0.0% |      - |    - | 7.1% |   0.0000 |
| DEGRADED |   48 |  115.2 | 6.2% | 0.302 | 0.1 |       48 | 0.0% |   0.0% |    - | 6.4% |   0.0208 |
|      ALL |  137 |   53.6 | 8.0% | 0.327 | 0.1 |      133 | 9.1% |  16.7% | 2.0× | 7.9% |   0.0451 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   18 |   11.2 | 38.9% | 0.672 | 0.5 |       15 | 83.3% |  55.6% | 1.4× | 16.7% |   0.6000 |
|       OK |    4 |   37.2 | 0.0% | 0.344 | 0.0 |        3 |    - |   0.0% |    - | 0.0% |   0.3333 |
| DEGRADED |    9 |  117.1 | 11.1% | 0.502 | 0.1 |        9 | 0.0% |   0.0% |    - | 14.3% |   0.2222 |
|      ALL |   31 |   45.3 | 25.8% | 0.580 | 0.3 |       27 | 71.4% |  41.7% | 1.6× | 13.3% |   0.4444 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   18 |   11.2 | 33.3% | 0.672 | 0.3 |       15 | 60.0% |  60.0% | 1.8× | 20.0% |   0.3333 |
|       OK |    4 |   37.2 | 0.0% | 0.292 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    9 |  117.1 | 0.0% | 0.418 | 0.0 |        9 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   45.3 | 19.4% | 0.550 | 0.2 |       27 | 60.0% |  60.0% | 3.2× | 9.1% |   0.1852 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   18 |   11.2 | 22.2% | 0.538 | 0.2 |       15 | 25.0% |  50.0% | 1.9× | 23.1% |   0.1333 |
|       OK |    4 |   37.2 | 0.0% | 0.268 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    9 |  117.1 | 11.1% | 0.436 | 0.1 |        9 | 0.0% |      - |    - | 11.1% |   0.0000 |
|      ALL |   31 |   45.3 | 16.1% | 0.474 | 0.2 |       27 | 20.0% |  50.0% | 2.7× | 16.0% |   0.0741 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available