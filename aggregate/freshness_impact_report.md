# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-07-24 UTC
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
|    FRESH |   60 |   12.4 | 18.3% | 0.513 | 0.2 |       56 | 80.0% |  29.6% | 1.7× | 6.9% |   0.4821 |
|       OK |   28 |   37.2 | 3.6% | 0.388 | 0.0 |       28 | 100.0% |  25.0% | 7.0× | 0.0% |   0.1429 |
| DEGRADED |   48 |  115.2 | 10.4% | 0.411 | 0.1 |       48 | 0.0% |   0.0% |    - | 13.9% |   0.2500 |
|      ALL |  136 |   53.8 | 12.5% | 0.451 | 0.1 |      132 | 56.2% |  20.9% | 1.7× | 7.9% |   0.3258 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   60 |   12.4 | 11.7% | 0.500 | 0.1 |       56 | 66.7% |  36.4% | 3.4× | 4.4% |   0.1964 |
|       OK |   28 |   37.2 | 0.0% | 0.321 | 0.0 |       28 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   48 |  115.2 | 0.0% | 0.334 | 0.0 |       48 |    - |   0.0% |    - | 0.0% |   0.0625 |
|      ALL |  136 |   53.8 | 5.1% | 0.405 | 0.1 |      132 | 66.7% |  28.6% | 6.3× | 1.7% |   0.1061 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   60 |   12.4 | 10.0% | 0.360 | 0.1 |       56 | 16.7% |  20.0% | 1.9× | 9.8% |   0.0893 |
|       OK |   28 |   37.2 | 7.1% | 0.306 | 0.1 |       28 | 0.0% |      - |    - | 7.1% |   0.0000 |
| DEGRADED |   48 |  115.2 | 6.2% | 0.302 | 0.1 |       48 | 0.0% |   0.0% |    - | 6.4% |   0.0208 |
|      ALL |  136 |   53.8 | 8.1% | 0.329 | 0.1 |      132 | 9.1% |  16.7% | 2.0× | 7.9% |   0.0455 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   18 |   11.2 | 38.9% | 0.672 | 0.5 |       14 | 83.3% |  62.5% | 1.5× | 16.7% |   0.5714 |
|       OK |    3 |   36.9 | 0.0% | 0.326 | 0.0 |        3 |    - |   0.0% |    - | 0.0% |   0.3333 |
| DEGRADED |   10 |  111.2 | 10.0% | 0.493 | 0.1 |       10 | 0.0% |   0.0% |    - | 12.5% |   0.2000 |
|      ALL |   31 |   46.0 | 25.8% | 0.581 | 0.3 |       27 | 71.4% |  45.5% | 1.8× | 12.5% |   0.4074 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   18 |   11.2 | 33.3% | 0.672 | 0.3 |       14 | 60.0% |  60.0% | 1.7× | 22.2% |   0.3571 |
|       OK |    3 |   36.9 | 0.0% | 0.306 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   10 |  111.2 | 0.0% | 0.400 | 0.0 |       10 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   46.0 | 19.4% | 0.549 | 0.2 |       27 | 60.0% |  60.0% | 3.2× | 9.1% |   0.1852 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   18 |   11.2 | 22.2% | 0.538 | 0.2 |       14 | 25.0% |  50.0% | 1.8× | 25.0% |   0.1429 |
|       OK |    3 |   36.9 | 0.0% | 0.314 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   10 |  111.2 | 10.0% | 0.405 | 0.1 |       10 | 0.0% |      - |    - | 10.0% |   0.0000 |
|      ALL |   31 |   46.0 | 16.1% | 0.473 | 0.2 |       27 | 20.0% |  50.0% | 2.7× | 16.0% |   0.0741 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available