# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-07-01 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (75.0%) is 75.0% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (2.3%) is 2.6× the overall rate (0.9%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   44 |   12.6 | 11.4% | 0.458 | 0.1 |       42 | 75.0% |  15.8% | 1.7× | 4.3% |   0.4524 |
|       OK |   25 |   37.2 | 4.0% | 0.396 | 0.0 |       25 | 100.0% |  33.3% | 8.3× | 0.0% |   0.1200 |
| DEGRADED |   44 |  116.4 | 11.4% | 0.423 | 0.1 |       42 | 0.0% |   0.0% |    - | 15.6% |   0.2381 |
|      ALL |  113 |   58.5 | 9.7% | 0.430 | 0.1 |      109 | 40.0% |  12.5% | 1.4× | 7.8% |   0.2936 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   44 |   12.6 | 2.3% | 0.443 | 0.0 |       42 | 100.0% |  16.7% | 7.0× | 0.0% |   0.1429 |
|       OK |   25 |   37.2 | 0.0% | 0.323 | 0.0 |       25 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   44 |  116.4 | 0.0% | 0.351 | 0.0 |       42 |    - |   0.0% |    - | 0.0% |   0.0714 |
|      ALL |  113 |   58.5 | 0.9% | 0.381 | 0.0 |      109 | 100.0% |  11.1% | 12.1× | 0.0% |   0.0826 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   44 |   12.6 | 4.5% | 0.295 | 0.1 |       42 | 0.0% |   0.0% |    - | 5.1% |   0.0714 |
|       OK |   25 |   37.2 | 8.0% | 0.305 | 0.1 |       25 | 0.0% |      - |    - | 8.0% |   0.0000 |
| DEGRADED |   44 |  116.4 | 6.8% | 0.310 | 0.1 |       42 | 0.0% |   0.0% |    - | 7.3% |   0.0238 |
|      ALL |  113 |   58.5 | 6.2% | 0.303 | 0.1 |      109 | 0.0% |   0.0% |    - | 6.7% |   0.0367 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   11.2 | 15.4% | 0.480 | 0.1 |       11 | 0.0% |   0.0% |    - | 14.3% |   0.3636 |
|       OK |    5 |   40.2 | 0.0% | 0.367 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |  102.9 | 7.7% | 0.501 | 0.1 |       11 | 0.0% |   0.0% |    - | 12.5% |   0.2727 |
|      ALL |   31 |   54.3 | 9.7% | 0.471 | 0.1 |       27 | 0.0% |   0.0% |    - | 10.0% |   0.2593 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   11.2 | 0.0% | 0.488 | 0.0 |       11 |    - |   0.0% |    - | 0.0% |   0.1818 |
|       OK |    5 |   40.2 | 0.0% | 0.284 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |  102.9 | 0.0% | 0.440 | 0.0 |       11 |    - |   0.0% |    - | 0.0% |   0.0909 |
|      ALL |   31 |   54.3 | 0.0% | 0.435 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.1111 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   11.2 | 7.7% | 0.426 | 0.1 |       11 | 0.0% |   0.0% |    - | 10.0% |   0.0909 |
|       OK |    5 |   40.2 | 20.0% | 0.337 | 0.2 |        5 | 0.0% |      - |    - | 20.0% |   0.0000 |
| DEGRADED |   13 |  102.9 | 15.4% | 0.468 | 0.1 |       11 | 0.0% |      - |    - | 18.2% |   0.0000 |
|      ALL |   31 |   54.3 | 12.9% | 0.429 | 0.1 |       27 | 0.0% |   0.0% |    - | 15.4% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available