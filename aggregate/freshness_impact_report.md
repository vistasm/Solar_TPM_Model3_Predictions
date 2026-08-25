# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-08-25 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (76.9%) is 76.9% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (10.3%) is 2.4× the overall rate (4.2%) — score distribution shift detected
🟢 **X+**: FRESH precision (16.7%) is 16.7% HIGHER than DEGRADED (0.0%) — fresher data is helping

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   68 |   12.5 | 22.1% | 0.522 | 0.3 |       66 | 76.9% |  32.3% | 1.6× | 8.6% |   0.4697 |
|       OK |   35 |   37.2 | 11.4% | 0.418 | 0.1 |       34 | 66.7% |  40.0% | 4.5× | 3.5% |   0.1471 |
| DEGRADED |   62 |  117.3 | 9.7% | 0.410 | 0.1 |       61 | 0.0% |   0.0% |    - | 10.6% |   0.2295 |
|      ALL |  165 |   57.1 | 15.2% | 0.458 | 0.2 |      161 | 57.1% |  24.0% | 1.8× | 8.1% |   0.3106 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   68 |   12.5 | 10.3% | 0.512 | 0.1 |       66 | 57.1% |  33.3% | 3.1× | 5.6% |   0.1818 |
|       OK |   35 |   37.2 | 0.0% | 0.352 | 0.0 |       34 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   62 |  117.3 | 0.0% | 0.342 | 0.0 |       61 |    - |   0.0% |    - | 0.0% |   0.0492 |
|      ALL |  165 |   57.1 | 4.2% | 0.414 | 0.0 |      161 | 57.1% |  26.7% | 6.1× | 2.1% |   0.0932 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   68 |   12.5 | 8.8% | 0.374 | 0.1 |       66 | 16.7% |  20.0% | 2.2× | 8.2% |   0.0758 |
|       OK |   35 |   37.2 | 5.7% | 0.320 | 0.1 |       34 | 0.0% |      - |    - | 5.9% |   0.0000 |
| DEGRADED |   62 |  117.3 | 4.8% | 0.293 | 0.1 |       61 | 0.0% |   0.0% |    - | 5.0% |   0.0164 |
|      ALL |  165 |   57.1 | 6.7% | 0.332 | 0.1 |      161 | 9.1% |  16.7% | 2.4× | 6.5% |   0.0373 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   13.7 | 50.0% | 0.589 | 0.8 |        6 | 50.0% |  50.0% | 1.5× | 25.0% |   0.3333 |
|       OK |    6 |   36.8 | 50.0% | 0.563 | 0.5 |        5 | 50.0% | 100.0% | 2.5× | 25.0% |   0.2000 |
| DEGRADED |   14 |  124.7 | 7.1% | 0.408 | 0.1 |       13 |    - |   0.0% |    - | 0.0% |   0.1538 |
|      ALL |   28 |   74.1 | 28.6% | 0.493 | 0.4 |       24 | 50.0% |  40.0% | 2.4× | 10.5% |   0.2083 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   13.7 | 0.0% | 0.601 | 0.0 |        6 |    - |   0.0% |    - | 0.0% |   0.1667 |
|       OK |    6 |   36.8 | 0.0% | 0.515 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   14 |  124.7 | 0.0% | 0.370 | 0.0 |       13 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   28 |   74.1 | 0.0% | 0.467 | 0.0 |       24 |    - |   0.0% |    - | 0.0% |   0.0417 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   13.7 | 0.0% | 0.475 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    6 |   36.8 | 0.0% | 0.417 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   14 |  124.7 | 0.0% | 0.261 | 0.0 |       13 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   28 |   74.1 | 0.0% | 0.356 | 0.0 |       24 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available