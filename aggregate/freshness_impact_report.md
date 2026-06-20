# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-06-20 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (75.0%) is 75.0% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (2.5%) is 2.6× the overall rate (1.0%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   40 |   12.9 | 10.0% | 0.445 | 0.1 |       39 | 75.0% |  17.6% | 1.7× | 4.5% |   0.4359 |
|       OK |   24 |   37.4 | 4.2% | 0.389 | 0.0 |       24 | 100.0% |  33.3% | 8.0× | 0.0% |   0.1250 |
| DEGRADED |   38 |  116.2 | 10.5% | 0.389 | 0.1 |       35 | 0.0% |   0.0% |    - | 15.4% |   0.2571 |
|      ALL |  102 |   57.1 | 8.8% | 0.411 | 0.1 |       98 | 44.4% |  13.8% | 1.5× | 7.2% |   0.2959 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   40 |   12.9 | 2.5% | 0.431 | 0.0 |       39 | 100.0% |  20.0% | 7.8× | 0.0% |   0.1282 |
|       OK |   24 |   37.4 | 0.0% | 0.321 | 0.0 |       24 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   38 |  116.2 | 0.0% | 0.316 | 0.0 |       35 |    - |   0.0% |    - | 0.0% |   0.0857 |
|      ALL |  102 |   57.1 | 1.0% | 0.362 | 0.0 |       98 | 100.0% |  12.5% | 12.2× | 0.0% |   0.0816 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   40 |   12.9 | 5.0% | 0.275 | 0.1 |       39 | 0.0% |   0.0% |    - | 5.6% |   0.0769 |
|       OK |   24 |   37.4 | 8.3% | 0.307 | 0.1 |       24 | 0.0% |      - |    - | 8.3% |   0.0000 |
| DEGRADED |   38 |  116.2 | 5.3% | 0.275 | 0.1 |       35 | 0.0% |   0.0% |    - | 5.9% |   0.0286 |
|      ALL |  102 |   57.1 | 5.9% | 0.283 | 0.1 |       98 | 0.0% |   0.0% |    - | 6.4% |   0.0408 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   13.6 | 9.1% | 0.404 | 0.1 |       10 | 0.0% |   0.0% |    - | 12.5% |   0.2000 |
|       OK |    7 |   42.8 | 0.0% | 0.377 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |   97.8 | 15.4% | 0.431 | 0.1 |       10 | 0.0% |   0.0% |    - | 33.3% |   0.4000 |
|      ALL |   31 |   55.5 | 9.7% | 0.409 | 0.1 |       27 | 0.0% |   0.0% |    - | 14.3% |   0.2222 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   13.6 | 0.0% | 0.408 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.1000 |
|       OK |    7 |   42.8 | 0.0% | 0.285 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |   97.8 | 0.0% | 0.340 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.1000 |
|      ALL |   31 |   55.5 | 0.0% | 0.352 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   13.6 | 9.1% | 0.340 | 0.1 |       10 | 0.0% |   0.0% |    - | 11.1% |   0.1000 |
|       OK |    7 |   42.8 | 14.3% | 0.391 | 0.1 |        7 | 0.0% |      - |    - | 14.3% |   0.0000 |
| DEGRADED |   13 |   97.8 | 7.7% | 0.396 | 0.1 |       10 | 0.0% |      - |    - | 10.0% |   0.0000 |
|      ALL |   31 |   55.5 | 9.7% | 0.375 | 0.1 |       27 | 0.0% |   0.0% |    - | 11.5% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available