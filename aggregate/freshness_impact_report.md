# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-08-09 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (81.8%) is 81.8% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (11.3%) is 2.4× the overall rate (4.6%) — score distribution shift detected
🟢 **X+**: FRESH precision (16.7%) is 16.7% HIGHER than DEGRADED (0.0%) — fresher data is helping

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   62 |   12.4 | 17.7% | 0.510 | 0.2 |       62 | 81.8% |  31.0% | 1.8× | 6.1% |   0.4677 |
|       OK |   32 |   36.7 | 6.2% | 0.402 | 0.1 |       32 | 50.0% |  25.0% | 4.0× | 3.6% |   0.1250 |
| DEGRADED |   58 |  117.3 | 8.6% | 0.408 | 0.1 |       54 | 0.0% |   0.0% |    - | 12.5% |   0.2593 |
|      ALL |  152 |   57.5 | 11.8% | 0.448 | 0.1 |      148 | 55.6% |  21.3% | 1.8× | 7.9% |   0.3176 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   62 |   12.4 | 11.3% | 0.498 | 0.1 |       62 | 57.1% |  36.4% | 3.2× | 5.9% |   0.1774 |
|       OK |   32 |   36.7 | 0.0% | 0.329 | 0.0 |       32 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   58 |  117.3 | 0.0% | 0.337 | 0.0 |       54 |    - |   0.0% |    - | 0.0% |   0.0556 |
|      ALL |  152 |   57.5 | 4.6% | 0.401 | 0.1 |      148 | 57.1% |  28.6% | 6.0× | 2.2% |   0.0946 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   62 |   12.4 | 9.7% | 0.357 | 0.1 |       62 | 16.7% |  20.0% | 2.1× | 8.8% |   0.0806 |
|       OK |   32 |   36.7 | 6.2% | 0.315 | 0.1 |       32 | 0.0% |      - |    - | 6.2% |   0.0000 |
| DEGRADED |   58 |  117.3 | 5.2% | 0.294 | 0.1 |       54 | 0.0% |   0.0% |    - | 5.7% |   0.0185 |
|      ALL |  152 |   57.5 | 7.2% | 0.324 | 0.1 |      148 | 9.1% |  16.7% | 2.2× | 7.0% |   0.0405 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   14.8 | 9.1% | 0.533 | 0.1 |       11 | 100.0% |  33.3% | 3.7× | 0.0% |   0.2727 |
|       OK |    6 |   36.4 | 16.7% | 0.403 | 0.2 |        6 | 0.0% |      - |    - | 16.7% |   0.0000 |
| DEGRADED |   14 |  119.8 | 0.0% | 0.359 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.3000 |
|      ALL |   31 |   66.4 | 6.5% | 0.429 | 0.1 |       27 | 50.0% |  16.7% | 2.2× | 4.8% |   0.2222 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   14.8 | 9.1% | 0.532 | 0.1 |       11 | 0.0% |      - |    - | 9.1% |   0.0000 |
|       OK |    6 |   36.4 | 0.0% | 0.306 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   14 |  119.8 | 0.0% | 0.290 | 0.0 |       10 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   66.4 | 3.2% | 0.379 | 0.0 |       27 | 0.0% |      - |    - | 3.7% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   14.8 | 0.0% | 0.363 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    6 |   36.4 | 0.0% | 0.306 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   14 |  119.8 | 0.0% | 0.244 | 0.0 |       10 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   66.4 | 0.0% | 0.298 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available