# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-07-26 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (81.8%) is 81.8% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (11.7%) is 2.3× the overall rate (5.1%) — score distribution shift detected
🟢 **X+**: FRESH precision (16.7%) is 16.7% HIGHER than DEGRADED (0.0%) — fresher data is helping

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   60 |   12.4 | 18.3% | 0.513 | 0.2 |       58 | 81.8% |  31.0% | 1.6× | 6.9% |   0.5000 |
|       OK |   29 |   37.2 | 3.5% | 0.389 | 0.0 |       28 | 100.0% |  25.0% | 7.0× | 0.0% |   0.1429 |
| DEGRADED |   49 |  114.1 | 10.2% | 0.412 | 0.1 |       48 | 0.0% |   0.0% |    - | 13.9% |   0.2500 |
|      ALL |  138 |   53.7 | 12.3% | 0.451 | 0.1 |      134 | 58.8% |  22.2% | 1.8× | 7.9% |   0.3358 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   60 |   12.4 | 11.7% | 0.500 | 0.1 |       58 | 57.1% |  36.4% | 3.0× | 6.4% |   0.1897 |
|       OK |   29 |   37.2 | 0.0% | 0.318 | 0.0 |       28 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   49 |  114.1 | 0.0% | 0.334 | 0.0 |       48 |    - |   0.0% |    - | 0.0% |   0.0625 |
|      ALL |  138 |   53.7 | 5.1% | 0.403 | 0.1 |      134 | 57.1% |  28.6% | 5.5× | 2.5% |   0.1045 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   60 |   12.4 | 10.0% | 0.360 | 0.1 |       58 | 16.7% |  20.0% | 1.9× | 9.4% |   0.0862 |
|       OK |   29 |   37.2 | 6.9% | 0.300 | 0.1 |       28 | 0.0% |      - |    - | 7.1% |   0.0000 |
| DEGRADED |   49 |  114.1 | 6.1% | 0.300 | 0.1 |       48 | 0.0% |   0.0% |    - | 6.4% |   0.0208 |
|      ALL |  138 |   53.7 | 8.0% | 0.326 | 0.1 |      134 | 9.1% |  16.7% | 2.0× | 7.8% |   0.0448 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   18 |   11.2 | 38.9% | 0.672 | 0.5 |       16 | 85.7% |  60.0% | 1.4× | 16.7% |   0.6250 |
|       OK |    4 |   37.2 | 0.0% | 0.344 | 0.0 |        3 |    - |   0.0% |    - | 0.0% |   0.3333 |
| DEGRADED |    9 |  114.9 | 11.1% | 0.476 | 0.1 |        8 | 0.0% |   0.0% |    - | 16.7% |   0.2500 |
|      ALL |   31 |   44.7 | 25.8% | 0.573 | 0.3 |       27 | 75.0% |  46.2% | 1.6× | 14.3% |   0.4815 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   18 |   11.2 | 33.3% | 0.672 | 0.3 |       16 | 50.0% |  60.0% | 1.6× | 27.3% |   0.3125 |
|       OK |    4 |   37.2 | 0.0% | 0.292 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    9 |  114.9 | 0.0% | 0.387 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   44.7 | 19.4% | 0.540 | 0.2 |       27 | 50.0% |  60.0% | 2.7× | 13.6% |   0.1852 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   18 |   11.2 | 22.2% | 0.538 | 0.2 |       16 | 25.0% |  50.0% | 2.0× | 21.4% |   0.1250 |
|       OK |    4 |   37.2 | 0.0% | 0.268 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    9 |  114.9 | 0.0% | 0.353 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   44.7 | 12.9% | 0.449 | 0.1 |       27 | 25.0% |  50.0% | 3.4× | 12.0% |   0.0741 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available