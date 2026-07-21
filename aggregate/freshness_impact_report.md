# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-07-21 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (80.0%) is 80.0% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (10.5%) is 2.3× the overall rate (4.5%) — score distribution shift detected
🟢 **X+**: FRESH precision (16.7%) is 16.7% HIGHER than DEGRADED (0.0%) — fresher data is helping

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   57 |   12.2 | 17.5% | 0.500 | 0.2 |       56 | 80.0% |  29.6% | 1.7× | 6.9% |   0.4821 |
|       OK |   28 |   37.2 | 3.6% | 0.388 | 0.0 |       28 | 100.0% |  25.0% | 7.0× | 0.0% |   0.1429 |
| DEGRADED |   48 |  115.2 | 10.4% | 0.411 | 0.1 |       45 | 0.0% |   0.0% |    - | 14.7% |   0.2444 |
|      ALL |  133 |   54.6 | 12.0% | 0.444 | 0.1 |      129 | 56.2% |  21.4% | 1.7× | 8.1% |   0.3256 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   57 |   12.2 | 10.5% | 0.483 | 0.1 |       56 | 66.7% |  36.4% | 3.4× | 4.4% |   0.1964 |
|       OK |   28 |   37.2 | 0.0% | 0.321 | 0.0 |       28 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   48 |  115.2 | 0.0% | 0.334 | 0.0 |       45 |    - |   0.0% |    - | 0.0% |   0.0667 |
|      ALL |  133 |   54.6 | 4.5% | 0.395 | 0.1 |      129 | 66.7% |  28.6% | 6.1× | 1.7% |   0.1085 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   57 |   12.2 | 10.5% | 0.345 | 0.1 |       56 | 16.7% |  20.0% | 1.9× | 9.8% |   0.0893 |
|       OK |   28 |   37.2 | 7.1% | 0.306 | 0.1 |       28 | 0.0% |      - |    - | 7.1% |   0.0000 |
| DEGRADED |   48 |  115.2 | 6.2% | 0.302 | 0.1 |       45 | 0.0% |   0.0% |    - | 6.8% |   0.0222 |
|      ALL |  133 |   54.6 | 8.3% | 0.321 | 0.1 |      129 | 9.1% |  16.7% | 1.9× | 8.1% |   0.0465 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   17 |   10.4 | 35.3% | 0.630 | 0.5 |       16 | 83.3% |  55.6% | 1.5× | 14.3% |   0.5625 |
|       OK |    4 |   36.2 | 0.0% | 0.384 | 0.0 |        4 |    - |   0.0% |    - | 0.0% |   0.2500 |
| DEGRADED |   10 |  111.2 | 10.0% | 0.493 | 0.1 |        7 | 0.0% |   0.0% |    - | 16.7% |   0.1429 |
|      ALL |   31 |   46.3 | 22.6% | 0.554 | 0.3 |       27 | 71.4% |  45.5% | 1.8× | 12.5% |   0.4074 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   17 |   10.4 | 29.4% | 0.607 | 0.3 |       16 | 60.0% |  50.0% | 1.6× | 20.0% |   0.3750 |
|       OK |    4 |   36.2 | 0.0% | 0.319 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   10 |  111.2 | 0.0% | 0.400 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   46.3 | 16.1% | 0.503 | 0.2 |       27 | 60.0% |  50.0% | 2.7× | 9.5% |   0.2222 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   17 |   10.4 | 23.5% | 0.508 | 0.2 |       16 | 25.0% |  50.0% | 2.0× | 21.4% |   0.1250 |
|       OK |    4 |   36.2 | 0.0% | 0.297 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   10 |  111.2 | 10.0% | 0.405 | 0.1 |        7 | 0.0% |      - |    - | 14.3% |   0.0000 |
|      ALL |   31 |   46.3 | 16.1% | 0.448 | 0.2 |       27 | 20.0% |  50.0% | 2.7× | 16.0% |   0.0741 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available