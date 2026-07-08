# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-07-08 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (87.5%) is 87.5% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (12.0%) is 2.4× the overall rate (5.0%) — score distribution shift detected
🟢 **X+**: FRESH precision (25.0%) is 25.0% HIGHER than DEGRADED (0.0%) — fresher data is helping

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   50 |   11.9 | 20.0% | 0.508 | 0.2 |       47 | 87.5% |  29.2% | 1.7× | 4.3% |   0.5106 |
|       OK |   26 |   36.7 | 3.9% | 0.401 | 0.0 |       25 | 100.0% |  33.3% | 8.3× | 0.0% |   0.1200 |
| DEGRADED |   44 |  116.4 | 11.4% | 0.423 | 0.1 |       44 | 0.0% |   0.0% |    - | 15.2% |   0.2500 |
|      ALL |  120 |   55.6 | 13.3% | 0.454 | 0.1 |      116 | 57.1% |  21.1% | 1.7× | 7.7% |   0.3276 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   50 |   11.9 | 12.0% | 0.495 | 0.1 |       47 | 75.0% |  30.0% | 3.5× | 2.7% |   0.2128 |
|       OK |   26 |   36.7 | 0.0% | 0.334 | 0.0 |       25 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   44 |  116.4 | 0.0% | 0.351 | 0.0 |       44 |    - |   0.0% |    - | 0.0% |   0.0682 |
|      ALL |  120 |   55.6 | 5.0% | 0.408 | 0.1 |      116 | 75.0% |  23.1% | 6.7× | 1.0% |   0.1121 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   50 |   11.9 | 12.0% | 0.360 | 0.1 |       47 | 25.0% |  20.0% | 2.4× | 7.1% |   0.1064 |
|       OK |   26 |   36.7 | 7.7% | 0.317 | 0.1 |       25 | 0.0% |      - |    - | 8.0% |   0.0000 |
| DEGRADED |   44 |  116.4 | 6.8% | 0.310 | 0.1 |       44 | 0.0% |   0.0% |    - | 7.0% |   0.0227 |
|      ALL |  120 |   55.6 | 9.2% | 0.332 | 0.1 |      116 | 11.1% |  16.7% | 2.1× | 7.3% |   0.0517 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |    9.1 | 46.7% | 0.654 | 0.6 |       12 | 80.0% |  57.1% | 1.4× | 20.0% |   0.5833 |
|       OK |    5 |   36.6 | 0.0% | 0.383 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   11 |  106.6 | 9.1% | 0.537 | 0.1 |       11 | 0.0% |   0.0% |    - | 11.1% |   0.1818 |
|      ALL |   31 |   48.1 | 25.8% | 0.569 | 0.3 |       27 | 66.7% |  44.4% | 2.0× | 11.1% |   0.3333 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |    9.1 | 33.3% | 0.653 | 0.3 |       12 | 66.7% |  40.0% | 1.6× | 14.3% |   0.4167 |
|       OK |    5 |   36.6 | 0.0% | 0.338 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   11 |  106.6 | 0.0% | 0.474 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   48.1 | 16.1% | 0.538 | 0.2 |       27 | 66.7% |  40.0% | 3.6× | 4.5% |   0.1852 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |    9.1 | 33.3% | 0.626 | 0.3 |       12 | 33.3% |  50.0% | 2.0× | 20.0% |   0.1667 |
|       OK |    5 |   36.6 | 0.0% | 0.280 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   11 |  106.6 | 18.2% | 0.519 | 0.2 |       11 | 0.0% |      - |    - | 18.2% |   0.0000 |
|      ALL |   31 |   48.1 | 22.6% | 0.532 | 0.2 |       27 | 20.0% |  50.0% | 2.7× | 16.0% |   0.0741 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available