# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-07-07 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (85.7%) is 85.7% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (12.2%) is 2.4× the overall rate (5.0%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   49 |   11.8 | 20.4% | 0.510 | 0.2 |       46 | 85.7% |  26.1% | 1.7× | 4.3% |   0.5000 |
|       OK |   26 |   36.7 | 3.9% | 0.401 | 0.0 |       25 | 100.0% |  33.3% | 8.3× | 0.0% |   0.1200 |
| DEGRADED |   44 |  116.4 | 11.4% | 0.423 | 0.1 |       44 | 0.0% |   0.0% |    - | 15.2% |   0.2500 |
|      ALL |  119 |   55.9 | 13.5% | 0.454 | 0.1 |      115 | 53.8% |  18.9% | 1.7× | 7.7% |   0.3217 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   49 |   11.8 | 12.2% | 0.497 | 0.1 |       46 | 66.7% |  22.2% | 3.4× | 2.7% |   0.1957 |
|       OK |   26 |   36.7 | 0.0% | 0.334 | 0.0 |       25 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   44 |  116.4 | 0.0% | 0.351 | 0.0 |       44 |    - |   0.0% |    - | 0.0% |   0.0682 |
|      ALL |  119 |   55.9 | 5.0% | 0.407 | 0.1 |      115 | 66.7% |  16.7% | 6.4× | 1.0% |   0.1043 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   49 |   11.8 | 12.2% | 0.362 | 0.1 |       46 | 0.0% |   0.0% |    - | 7.1% |   0.0870 |
|       OK |   26 |   36.7 | 7.7% | 0.317 | 0.1 |       25 | 0.0% |      - |    - | 8.0% |   0.0000 |
| DEGRADED |   44 |  116.4 | 6.8% | 0.310 | 0.1 |       44 | 0.0% |   0.0% |    - | 7.0% |   0.0227 |
|      ALL |  119 |   55.9 | 9.2% | 0.333 | 0.1 |      115 | 0.0% |   0.0% |    - | 7.3% |   0.0435 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |    9.1 | 46.7% | 0.652 | 0.6 |       12 | 75.0% |  50.0% | 1.5× | 16.7% |   0.5000 |
|       OK |    5 |   36.6 | 0.0% | 0.383 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   11 |  106.6 | 9.1% | 0.537 | 0.1 |       11 | 0.0% |   0.0% |    - | 11.1% |   0.1818 |
|      ALL |   31 |   48.1 | 25.8% | 0.568 | 0.3 |       27 | 60.0% |  37.5% | 2.0× | 10.5% |   0.2963 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |    9.1 | 33.3% | 0.655 | 0.3 |       12 | 50.0% |  25.0% | 1.5× | 12.5% |   0.3333 |
|       OK |    5 |   36.6 | 0.0% | 0.338 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   11 |  106.6 | 0.0% | 0.474 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   48.1 | 16.1% | 0.539 | 0.2 |       27 | 50.0% |  25.0% | 3.4× | 4.3% |   0.1481 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |    9.1 | 33.3% | 0.624 | 0.3 |       12 | 0.0% |   0.0% |    - | 18.2% |   0.0833 |
|       OK |    5 |   36.6 | 0.0% | 0.280 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   11 |  106.6 | 18.2% | 0.519 | 0.2 |       11 | 0.0% |      - |    - | 18.2% |   0.0000 |
|      ALL |   31 |   48.1 | 22.6% | 0.531 | 0.2 |       27 | 0.0% |   0.0% |    - | 15.4% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available