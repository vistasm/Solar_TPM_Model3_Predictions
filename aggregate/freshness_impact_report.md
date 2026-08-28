# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-08-28 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (71.4%) is 54.8% HIGHER than DEGRADED (16.7%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (10.0%) is 2.4× the overall rate (4.2%) — score distribution shift detected
🟢 **X+**: FRESH precision (16.7%) is 16.7% HIGHER than DEGRADED (0.0%) — fresher data is helping

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   70 |   12.5 | 24.3% | 0.528 | 0.3 |       67 | 71.4% |  32.3% | 1.5× | 11.1% |   0.4627 |
|       OK |   36 |   37.0 | 13.9% | 0.426 | 0.1 |       35 | 50.0% |  40.0% | 3.5× | 6.7% |   0.1429 |
| DEGRADED |   62 |  117.3 | 9.7% | 0.410 | 0.1 |       62 | 16.7% |   6.7% | 0.7× | 10.6% |   0.2419 |
|      ALL |  168 |   56.4 | 16.7% | 0.463 | 0.2 |      164 | 54.2% |  25.5% | 1.7× | 9.7% |   0.3110 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   70 |   12.5 | 10.0% | 0.520 | 0.1 |       67 | 57.1% |  33.3% | 3.2× | 5.5% |   0.1791 |
|       OK |   36 |   37.0 | 0.0% | 0.364 | 0.0 |       35 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   62 |  117.3 | 0.0% | 0.342 | 0.0 |       62 |    - |   0.0% |    - | 0.0% |   0.0484 |
|      ALL |  168 |   56.4 | 4.2% | 0.421 | 0.0 |      164 | 57.1% |  26.7% | 6.2× | 2.0% |   0.0915 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   70 |   12.5 | 8.6% | 0.374 | 0.1 |       67 | 16.7% |  20.0% | 2.2× | 8.1% |   0.0746 |
|       OK |   36 |   37.0 | 5.6% | 0.322 | 0.1 |       35 | 0.0% |      - |    - | 5.7% |   0.0000 |
| DEGRADED |   62 |  117.3 | 4.8% | 0.293 | 0.1 |       62 | 0.0% |   0.0% |    - | 4.9% |   0.0161 |
|      ALL |  168 |   56.4 | 6.6% | 0.333 | 0.1 |      164 | 9.1% |  16.7% | 2.5× | 6.3% |   0.0366 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   13.3 | 66.7% | 0.648 | 0.9 |        6 | 33.3% |  50.0% | 1.0× | 50.0% |   0.3333 |
|       OK |    6 |   37.6 | 66.7% | 0.606 | 0.7 |        5 | 33.3% | 100.0% | 1.7× | 50.0% |   0.2000 |
| DEGRADED |   13 |  129.5 | 7.7% | 0.403 | 0.1 |       13 | 100.0% |  50.0% | 6.5× | 0.0% |   0.1538 |
|      ALL |   28 |   72.5 | 39.3% | 0.525 | 0.5 |       24 | 42.9% |  60.0% | 2.1× | 21.1% |   0.2083 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   13.3 | 0.0% | 0.674 | 0.0 |        6 |    - |   0.0% |    - | 0.0% |   0.1667 |
|       OK |    6 |   37.6 | 0.0% | 0.606 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |  129.5 | 0.0% | 0.370 | 0.0 |       13 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   28 |   72.5 | 0.0% | 0.519 | 0.0 |       24 |    - |   0.0% |    - | 0.0% |   0.0417 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   13.3 | 0.0% | 0.498 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    6 |   37.6 | 0.0% | 0.391 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |  129.5 | 0.0% | 0.266 | 0.0 |       13 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   28 |   72.5 | 0.0% | 0.367 | 0.0 |       24 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available