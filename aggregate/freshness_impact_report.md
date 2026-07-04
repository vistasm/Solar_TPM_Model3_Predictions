# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-07-04 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (75.0%) is 75.0% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (8.5%) is 2.5× the overall rate (3.5%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   47 |   12.0 | 17.0% | 0.490 | 0.2 |       43 | 75.0% |  15.0% | 1.6× | 4.3% |   0.4651 |
|       OK |   25 |   37.2 | 4.0% | 0.396 | 0.0 |       25 | 100.0% |  33.3% | 8.3× | 0.0% |   0.1200 |
| DEGRADED |   44 |  116.4 | 11.4% | 0.423 | 0.1 |       44 | 0.0% |   0.0% |    - | 15.2% |   0.2500 |
|      ALL |  116 |   57.1 | 12.1% | 0.445 | 0.1 |      112 | 40.0% |  11.8% | 1.3× | 7.7% |   0.3036 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   47 |   12.0 | 8.5% | 0.477 | 0.1 |       43 | 100.0% |  14.3% | 6.1× | 0.0% |   0.1628 |
|       OK |   25 |   37.2 | 0.0% | 0.323 | 0.0 |       25 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   44 |  116.4 | 0.0% | 0.351 | 0.0 |       44 |    - |   0.0% |    - | 0.0% |   0.0682 |
|      ALL |  116 |   57.1 | 3.5% | 0.396 | 0.0 |      112 | 100.0% |  10.0% | 11.2× | 0.0% |   0.0893 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   47 |   12.0 | 8.5% | 0.338 | 0.1 |       43 | 0.0% |   0.0% |    - | 5.1% |   0.0930 |
|       OK |   25 |   37.2 | 8.0% | 0.305 | 0.1 |       25 | 0.0% |      - |    - | 8.0% |   0.0000 |
| DEGRADED |   44 |  116.4 | 6.8% | 0.310 | 0.1 |       44 | 0.0% |   0.0% |    - | 7.0% |   0.0227 |
|      ALL |  116 |   57.1 | 7.8% | 0.320 | 0.1 |      112 | 0.0% |   0.0% |    - | 6.5% |   0.0446 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |   10.4 | 33.3% | 0.583 | 0.5 |       11 | 0.0% |   0.0% |    - | 14.3% |   0.3636 |
|       OK |    5 |   40.2 | 0.0% | 0.367 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   11 |  106.6 | 9.1% | 0.537 | 0.1 |       11 | 0.0% |   0.0% |    - | 11.1% |   0.1818 |
|      ALL |   31 |   49.3 | 19.4% | 0.532 | 0.3 |       27 | 0.0% |   0.0% |    - | 9.5% |   0.2222 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |   10.4 | 20.0% | 0.598 | 0.2 |       11 |    - |   0.0% |    - | 0.0% |   0.1818 |
|       OK |    5 |   40.2 | 0.0% | 0.284 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   11 |  106.6 | 0.0% | 0.474 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   49.3 | 9.7% | 0.503 | 0.1 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |   10.4 | 20.0% | 0.540 | 0.2 |       11 | 0.0% |   0.0% |    - | 10.0% |   0.0909 |
|       OK |    5 |   40.2 | 20.0% | 0.337 | 0.2 |        5 | 0.0% |      - |    - | 20.0% |   0.0000 |
| DEGRADED |   11 |  106.6 | 18.2% | 0.519 | 0.2 |       11 | 0.0% |      - |    - | 18.2% |   0.0000 |
|      ALL |   31 |   49.3 | 19.4% | 0.500 | 0.2 |       27 | 0.0% |   0.0% |    - | 15.4% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available