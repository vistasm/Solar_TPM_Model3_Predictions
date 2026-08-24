# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-08-24 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (76.9%) is 76.9% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (10.4%) is 2.4× the overall rate (4.3%) — score distribution shift detected
🟢 **X+**: FRESH precision (16.7%) is 16.7% HIGHER than DEGRADED (0.0%) — fresher data is helping

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   67 |   12.6 | 20.9% | 0.519 | 0.3 |       65 | 76.9% |  33.3% | 1.7× | 8.6% |   0.4615 |
|       OK |   35 |   37.2 | 11.4% | 0.418 | 0.1 |       34 | 66.7% |  40.0% | 4.5× | 3.5% |   0.1471 |
| DEGRADED |   62 |  117.3 | 9.7% | 0.410 | 0.1 |       61 | 0.0% |   0.0% |    - | 10.6% |   0.2295 |
|      ALL |  164 |   57.4 | 14.6% | 0.456 | 0.2 |      160 | 57.1% |  24.5% | 1.9× | 8.1% |   0.3063 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   67 |   12.6 | 10.4% | 0.508 | 0.1 |       65 | 57.1% |  33.3% | 3.1× | 5.7% |   0.1846 |
|       OK |   35 |   37.2 | 0.0% | 0.352 | 0.0 |       34 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   62 |  117.3 | 0.0% | 0.342 | 0.0 |       61 |    - |   0.0% |    - | 0.0% |   0.0492 |
|      ALL |  164 |   57.4 | 4.3% | 0.412 | 0.0 |      160 | 57.1% |  26.7% | 6.1× | 2.1% |   0.0938 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   67 |   12.6 | 9.0% | 0.373 | 0.1 |       65 | 16.7% |  20.0% | 2.2× | 8.3% |   0.0769 |
|       OK |   35 |   37.2 | 5.7% | 0.320 | 0.1 |       34 | 0.0% |      - |    - | 5.9% |   0.0000 |
| DEGRADED |   62 |  117.3 | 4.8% | 0.293 | 0.1 |       61 | 0.0% |   0.0% |    - | 5.0% |   0.0164 |
|      ALL |  164 |   57.4 | 6.7% | 0.332 | 0.1 |      160 | 9.1% |  16.7% | 2.4× | 6.5% |   0.0375 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    7 |   15.0 | 42.9% | 0.569 | 0.7 |        5 | 50.0% | 100.0% | 2.5× | 25.0% |   0.2000 |
|       OK |    7 |   37.0 | 42.9% | 0.540 | 0.4 |        6 | 50.0% | 100.0% | 3.0× | 20.0% |   0.1667 |
| DEGRADED |   14 |  124.7 | 7.1% | 0.408 | 0.1 |       13 |    - |   0.0% |    - | 0.0% |   0.1538 |
|      ALL |   28 |   75.4 | 25.0% | 0.481 | 0.3 |       24 | 50.0% |  50.0% | 3.0× | 10.0% |   0.1667 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    7 |   15.0 | 0.0% | 0.578 | 0.0 |        5 |    - |   0.0% |    - | 0.0% |   0.2000 |
|       OK |    7 |   37.0 | 0.0% | 0.478 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   14 |  124.7 | 0.0% | 0.370 | 0.0 |       13 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   28 |   75.4 | 0.0% | 0.449 | 0.0 |       24 |    - |   0.0% |    - | 0.0% |   0.0417 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    7 |   15.0 | 0.0% | 0.487 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    7 |   37.0 | 0.0% | 0.376 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   14 |  124.7 | 0.0% | 0.261 | 0.0 |       13 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   28 |   75.4 | 0.0% | 0.346 | 0.0 |       24 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available