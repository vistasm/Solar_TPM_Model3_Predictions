# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-09-05 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (70.6%) is 53.9% HIGHER than DEGRADED (16.7%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (9.5%) is 2.4× the overall rate (4.0%) — score distribution shift detected
🟢 **X+**: FRESH precision (16.7%) is 16.7% HIGHER than DEGRADED (0.0%) — fresher data is helping

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   74 |   12.5 | 24.3% | 0.526 | 0.3 |       70 | 70.6% |  36.4% | 1.5× | 13.5% |   0.4714 |
|       OK |   38 |   36.5 | 13.2% | 0.418 | 0.1 |       38 | 40.0% |  40.0% | 3.0× | 9.1% |   0.1316 |
| DEGRADED |   64 |  115.8 | 9.4% | 0.406 | 0.1 |       64 | 16.7% |   6.7% | 0.7× | 10.2% |   0.2344 |
|      ALL |  176 |   55.2 | 16.5% | 0.459 | 0.2 |      172 | 53.6% |  28.3% | 1.7× | 10.9% |   0.3081 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   74 |   12.5 | 9.5% | 0.513 | 0.1 |       70 | 57.1% |  30.8% | 3.1× | 5.3% |   0.1857 |
|       OK |   38 |   36.5 | 0.0% | 0.354 | 0.0 |       38 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   64 |  115.8 | 0.0% | 0.338 | 0.0 |       64 |    - |   0.0% |    - | 0.0% |   0.0469 |
|      ALL |  176 |   55.2 | 4.0% | 0.415 | 0.0 |      172 | 57.1% |  25.0% | 6.1× | 1.9% |   0.0930 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   74 |   12.5 | 9.5% | 0.385 | 0.1 |       70 | 16.7% |  20.0% | 2.3× | 7.7% |   0.0714 |
|       OK |   38 |   36.5 | 5.3% | 0.310 | 0.1 |       38 | 0.0% |      - |    - | 5.3% |   0.0000 |
| DEGRADED |   64 |  115.8 | 4.7% | 0.287 | 0.1 |       64 | 0.0% |   0.0% |    - | 4.8% |   0.0156 |
|      ALL |  176 |   55.2 | 6.8% | 0.333 | 0.1 |      172 | 9.1% |  16.7% | 2.6× | 6.0% |   0.0349 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   12.9 | 58.3% | 0.606 | 0.8 |        8 | 50.0% |  75.0% | 1.0× | 75.0% |   0.5000 |
|       OK |    6 |   35.4 | 50.0% | 0.508 | 0.5 |        6 | 33.3% | 100.0% | 2.0× | 40.0% |   0.1667 |
| DEGRADED |   10 |  137.8 | 10.0% | 0.321 | 0.1 |       10 | 100.0% | 100.0% | 10.0× | 0.0% |   0.1000 |
|      ALL |   28 |   62.4 | 39.3% | 0.483 | 0.5 |       24 | 50.0% |  83.3% | 2.0× | 27.8% |   0.2500 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   12.9 | 0.0% | 0.587 | 0.0 |        8 |    - |   0.0% |    - | 0.0% |   0.2500 |
|       OK |    6 |   35.4 | 0.0% | 0.488 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   10 |  137.8 | 0.0% | 0.263 | 0.0 |       10 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   28 |   62.4 | 0.0% | 0.450 | 0.0 |       24 |    - |   0.0% |    - | 0.0% |   0.0833 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   12.9 | 8.3% | 0.530 | 0.1 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    6 |   35.4 | 0.0% | 0.281 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   10 |  137.8 | 0.0% | 0.201 | 0.0 |       10 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   28 |   62.4 | 3.6% | 0.359 | 0.0 |       24 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available