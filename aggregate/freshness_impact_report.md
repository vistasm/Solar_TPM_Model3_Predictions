# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-07-22 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (80.0%) is 80.0% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (12.1%) is 2.3× the overall rate (5.2%) — score distribution shift detected
🟢 **X+**: FRESH precision (16.7%) is 16.7% HIGHER than DEGRADED (0.0%) — fresher data is helping

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   58 |   12.2 | 19.0% | 0.507 | 0.2 |       56 | 80.0% |  29.6% | 1.7× | 6.9% |   0.4821 |
|       OK |   28 |   37.2 | 3.6% | 0.388 | 0.0 |       28 | 100.0% |  25.0% | 7.0× | 0.0% |   0.1429 |
| DEGRADED |   48 |  115.2 | 10.4% | 0.411 | 0.1 |       46 | 0.0% |   0.0% |    - | 14.3% |   0.2391 |
|      ALL |  134 |   54.3 | 12.7% | 0.448 | 0.1 |      130 | 56.2% |  21.4% | 1.7× | 8.0% |   0.3231 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   58 |   12.2 | 12.1% | 0.491 | 0.1 |       56 | 66.7% |  36.4% | 3.4× | 4.4% |   0.1964 |
|       OK |   28 |   37.2 | 0.0% | 0.321 | 0.0 |       28 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   48 |  115.2 | 0.0% | 0.334 | 0.0 |       46 |    - |   0.0% |    - | 0.0% |   0.0652 |
|      ALL |  134 |   54.3 | 5.2% | 0.399 | 0.1 |      130 | 66.7% |  28.6% | 6.2× | 1.7% |   0.1077 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   58 |   12.2 | 10.3% | 0.349 | 0.1 |       56 | 16.7% |  20.0% | 1.9× | 9.8% |   0.0893 |
|       OK |   28 |   37.2 | 7.1% | 0.306 | 0.1 |       28 | 0.0% |      - |    - | 7.1% |   0.0000 |
| DEGRADED |   48 |  115.2 | 6.2% | 0.302 | 0.1 |       46 | 0.0% |   0.0% |    - | 6.7% |   0.0217 |
|      ALL |  134 |   54.3 | 8.2% | 0.323 | 0.1 |      130 | 9.1% |  16.7% | 2.0× | 8.1% |   0.0462 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   17 |   10.3 | 41.2% | 0.662 | 0.5 |       15 | 83.3% |  62.5% | 1.6× | 14.3% |   0.5333 |
|       OK |    4 |   36.2 | 0.0% | 0.384 | 0.0 |        4 |    - |   0.0% |    - | 0.0% |   0.2500 |
| DEGRADED |   10 |  111.2 | 10.0% | 0.493 | 0.1 |        8 | 0.0% |   0.0% |    - | 14.3% |   0.1250 |
|      ALL |   31 |   46.2 | 25.8% | 0.572 | 0.3 |       27 | 71.4% |  50.0% | 1.9× | 11.8% |   0.3704 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   17 |   10.3 | 35.3% | 0.645 | 0.3 |       15 | 60.0% |  60.0% | 1.8× | 20.0% |   0.3333 |
|       OK |    4 |   36.2 | 0.0% | 0.319 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   10 |  111.2 | 0.0% | 0.400 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   46.2 | 19.4% | 0.524 | 0.2 |       27 | 60.0% |  60.0% | 3.2× | 9.1% |   0.1852 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   17 |   10.3 | 23.5% | 0.501 | 0.2 |       15 | 25.0% |  50.0% | 1.9× | 23.1% |   0.1333 |
|       OK |    4 |   36.2 | 0.0% | 0.297 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   10 |  111.2 | 10.0% | 0.405 | 0.1 |        8 | 0.0% |      - |    - | 12.5% |   0.0000 |
|      ALL |   31 |   46.2 | 16.1% | 0.444 | 0.2 |       27 | 20.0% |  50.0% | 2.7× | 16.0% |   0.0741 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available