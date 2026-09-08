# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-09-08 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (70.6%) is 53.9% HIGHER than DEGRADED (16.7%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (9.2%) is 2.4× the overall rate (3.9%) — score distribution shift detected
🟢 **X+**: FRESH precision (16.7%) is 16.7% HIGHER than DEGRADED (0.0%) — fresher data is helping

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   76 |   12.6 | 23.7% | 0.521 | 0.3 |       73 | 70.6% |  34.3% | 1.5× | 13.2% |   0.4795 |
|       OK |   39 |   36.6 | 12.8% | 0.413 | 0.1 |       38 | 40.0% |  40.0% | 3.0× | 9.1% |   0.1316 |
| DEGRADED |   64 |  115.8 | 9.4% | 0.406 | 0.1 |       64 | 16.7% |   6.7% | 0.7× | 10.2% |   0.2344 |
|      ALL |  179 |   54.7 | 16.2% | 0.456 | 0.2 |      175 | 53.6% |  27.3% | 1.7× | 10.8% |   0.3143 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   76 |   12.6 | 9.2% | 0.507 | 0.1 |       73 | 57.1% |  30.8% | 3.2× | 5.0% |   0.1781 |
|       OK |   39 |   36.6 | 0.0% | 0.350 | 0.0 |       38 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   64 |  115.8 | 0.0% | 0.338 | 0.0 |       64 |    - |   0.0% |    - | 0.0% |   0.0469 |
|      ALL |  179 |   54.7 | 3.9% | 0.413 | 0.0 |      175 | 57.1% |  25.0% | 6.2× | 1.9% |   0.0914 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   76 |   12.6 | 9.2% | 0.385 | 0.1 |       73 | 16.7% |  20.0% | 2.4× | 7.3% |   0.0685 |
|       OK |   39 |   36.6 | 5.1% | 0.307 | 0.1 |       38 | 0.0% |      - |    - | 5.3% |   0.0000 |
| DEGRADED |   64 |  115.8 | 4.7% | 0.287 | 0.1 |       64 | 0.0% |   0.0% |    - | 4.8% |   0.0156 |
|      ALL |  179 |   54.7 | 6.7% | 0.333 | 0.1 |      175 | 9.1% |  16.7% | 2.6× | 5.9% |   0.0343 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   13.3 | 50.0% | 0.568 | 0.6 |       11 | 50.0% |  50.0% | 0.9× | 60.0% |   0.5455 |
|       OK |    7 |   36.5 | 42.9% | 0.464 | 0.4 |        6 | 33.3% | 100.0% | 2.0× | 40.0% |   0.1667 |
| DEGRADED |    7 |  119.5 | 14.3% | 0.354 | 0.1 |        7 | 100.0% | 100.0% | 7.0× | 0.0% |   0.1429 |
|      ALL |   28 |   45.6 | 39.3% | 0.488 | 0.5 |       24 | 50.0% |  62.5% | 1.5× | 31.2% |   0.3333 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   13.3 | 0.0% | 0.548 | 0.0 |       11 |    - |   0.0% |    - | 0.0% |   0.1818 |
|       OK |    7 |   36.5 | 0.0% | 0.445 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    7 |  119.5 | 0.0% | 0.309 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   28 |   45.6 | 0.0% | 0.463 | 0.0 |       24 |    - |   0.0% |    - | 0.0% |   0.0833 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   13.3 | 7.1% | 0.506 | 0.1 |       11 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    7 |   36.5 | 0.0% | 0.269 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    7 |  119.5 | 0.0% | 0.191 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   28 |   45.6 | 3.6% | 0.368 | 0.0 |       24 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available