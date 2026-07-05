# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-07-05 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (80.0%) is 80.0% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (10.4%) is 2.4× the overall rate (4.3%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   48 |   11.9 | 18.8% | 0.500 | 0.2 |       44 | 80.0% |  19.1% | 1.7× | 4.3% |   0.4773 |
|       OK |   25 |   37.2 | 4.0% | 0.396 | 0.0 |       25 | 100.0% |  33.3% | 8.3× | 0.0% |   0.1200 |
| DEGRADED |   44 |  116.4 | 11.4% | 0.423 | 0.1 |       44 | 0.0% |   0.0% |    - | 15.2% |   0.2500 |
|      ALL |  117 |   56.6 | 12.8% | 0.449 | 0.1 |      113 | 45.5% |  14.3% | 1.5× | 7.7% |   0.3097 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   48 |   11.9 | 10.4% | 0.488 | 0.1 |       44 | 100.0% |  12.5% | 5.5× | 0.0% |   0.1818 |
|       OK |   25 |   37.2 | 0.0% | 0.323 | 0.0 |       25 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   44 |  116.4 | 0.0% | 0.351 | 0.0 |       44 |    - |   0.0% |    - | 0.0% |   0.0682 |
|      ALL |  117 |   56.6 | 4.3% | 0.401 | 0.0 |      113 | 100.0% |   9.1% | 10.3× | 0.0% |   0.0973 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   48 |   11.9 | 10.4% | 0.351 | 0.1 |       44 | 0.0% |   0.0% |    - | 5.0% |   0.0909 |
|       OK |   25 |   37.2 | 8.0% | 0.305 | 0.1 |       25 | 0.0% |      - |    - | 8.0% |   0.0000 |
| DEGRADED |   44 |  116.4 | 6.8% | 0.310 | 0.1 |       44 | 0.0% |   0.0% |    - | 7.0% |   0.0227 |
|      ALL |  117 |   56.6 | 8.6% | 0.326 | 0.1 |      113 | 0.0% |   0.0% |    - | 6.5% |   0.0442 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |    9.5 | 40.0% | 0.618 | 0.5 |       11 | 50.0% |  20.0% | 1.1× | 16.7% |   0.4545 |
|       OK |    5 |   40.2 | 0.0% | 0.367 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   11 |  106.6 | 9.1% | 0.537 | 0.1 |       11 | 0.0% |   0.0% |    - | 11.1% |   0.1818 |
|      ALL |   31 |   48.9 | 22.6% | 0.549 | 0.3 |       27 | 33.3% |  14.3% | 1.3× | 10.0% |   0.2593 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |    9.5 | 26.7% | 0.628 | 0.3 |       11 |    - |   0.0% |    - | 0.0% |   0.2727 |
|       OK |    5 |   40.2 | 0.0% | 0.284 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   11 |  106.6 | 0.0% | 0.474 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   48.9 | 12.9% | 0.518 | 0.1 |       27 |    - |   0.0% |    - | 0.0% |   0.1111 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |    9.5 | 26.7% | 0.588 | 0.3 |       11 | 0.0% |   0.0% |    - | 10.0% |   0.0909 |
|       OK |    5 |   40.2 | 20.0% | 0.337 | 0.2 |        5 | 0.0% |      - |    - | 20.0% |   0.0000 |
| DEGRADED |   11 |  106.6 | 18.2% | 0.519 | 0.2 |       11 | 0.0% |      - |    - | 18.2% |   0.0000 |
|      ALL |   31 |   48.9 | 22.6% | 0.523 | 0.2 |       27 | 0.0% |   0.0% |    - | 15.4% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available