# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-09-07 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (70.6%) is 53.9% HIGHER than DEGRADED (16.7%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (9.2%) is 2.3× the overall rate (3.9%) — score distribution shift detected
🟢 **X+**: FRESH precision (16.7%) is 16.7% HIGHER than DEGRADED (0.0%) — fresher data is helping

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   76 |   12.6 | 23.7% | 0.521 | 0.3 |       72 | 70.6% |  35.3% | 1.5× | 13.2% |   0.4722 |
|       OK |   38 |   36.5 | 13.2% | 0.418 | 0.1 |       38 | 40.0% |  40.0% | 3.0× | 9.1% |   0.1316 |
| DEGRADED |   64 |  115.8 | 9.4% | 0.406 | 0.1 |       64 | 16.7% |   6.7% | 0.7× | 10.2% |   0.2344 |
|      ALL |  178 |   54.8 | 16.3% | 0.458 | 0.2 |      174 | 53.6% |  27.8% | 1.7× | 10.8% |   0.3103 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   76 |   12.6 | 9.2% | 0.507 | 0.1 |       72 | 57.1% |  30.8% | 3.2× | 5.1% |   0.1806 |
|       OK |   38 |   36.5 | 0.0% | 0.354 | 0.0 |       38 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   64 |  115.8 | 0.0% | 0.338 | 0.0 |       64 |    - |   0.0% |    - | 0.0% |   0.0469 |
|      ALL |  178 |   54.8 | 3.9% | 0.414 | 0.0 |      174 | 57.1% |  25.0% | 6.2× | 1.9% |   0.0920 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   76 |   12.6 | 9.2% | 0.385 | 0.1 |       72 | 16.7% |  20.0% | 2.4× | 7.5% |   0.0694 |
|       OK |   38 |   36.5 | 5.3% | 0.310 | 0.1 |       38 | 0.0% |      - |    - | 5.3% |   0.0000 |
| DEGRADED |   64 |  115.8 | 4.7% | 0.287 | 0.1 |       64 | 0.0% |   0.0% |    - | 4.8% |   0.0156 |
|      ALL |  178 |   54.8 | 6.7% | 0.334 | 0.1 |      174 | 9.1% |  16.7% | 2.6× | 5.9% |   0.0345 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   13.3 | 50.0% | 0.568 | 0.6 |       10 | 50.0% |  60.0% | 1.0× | 60.0% |   0.5000 |
|       OK |    6 |   35.4 | 50.0% | 0.508 | 0.5 |        6 | 33.3% | 100.0% | 2.0× | 40.0% |   0.1667 |
| DEGRADED |    8 |  130.2 | 12.5% | 0.329 | 0.1 |        8 | 100.0% | 100.0% | 8.0× | 0.0% |   0.1250 |
|      ALL |   28 |   51.4 | 39.3% | 0.487 | 0.5 |       24 | 50.0% |  71.4% | 1.7× | 29.4% |   0.2917 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   13.3 | 0.0% | 0.548 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.2000 |
|       OK |    6 |   35.4 | 0.0% | 0.488 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    8 |  130.2 | 0.0% | 0.281 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   28 |   51.4 | 0.0% | 0.459 | 0.0 |       24 |    - |   0.0% |    - | 0.0% |   0.0833 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   13.3 | 7.1% | 0.506 | 0.1 |       10 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    6 |   35.4 | 0.0% | 0.281 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    8 |  130.2 | 0.0% | 0.175 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   28 |   51.4 | 3.6% | 0.363 | 0.0 |       24 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available