# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-08-23 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (75.0%) is 75.0% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (10.4%) is 2.4× the overall rate (4.3%) — score distribution shift detected
🟢 **X+**: FRESH precision (16.7%) is 16.7% HIGHER than DEGRADED (0.0%) — fresher data is helping

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   67 |   12.6 | 20.9% | 0.519 | 0.3 |       64 | 75.0% |  31.0% | 1.7× | 8.6% |   0.4531 |
|       OK |   35 |   37.2 | 11.4% | 0.418 | 0.1 |       34 | 66.7% |  40.0% | 4.5× | 3.5% |   0.1471 |
| DEGRADED |   61 |  118.1 | 8.2% | 0.406 | 0.1 |       61 | 0.0% |   0.0% |    - | 10.6% |   0.2295 |
|      ALL |  163 |   57.4 | 14.1% | 0.455 | 0.2 |      159 | 55.0% |  22.9% | 1.8× | 8.1% |   0.3019 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   67 |   12.6 | 10.4% | 0.508 | 0.1 |       64 | 57.1% |  36.4% | 3.3× | 5.7% |   0.1719 |
|       OK |   35 |   37.2 | 0.0% | 0.352 | 0.0 |       34 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   61 |  118.1 | 0.0% | 0.337 | 0.0 |       61 |    - |   0.0% |    - | 0.0% |   0.0492 |
|      ALL |  163 |   57.4 | 4.3% | 0.410 | 0.0 |      159 | 57.1% |  28.6% | 6.5× | 2.1% |   0.0881 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   67 |   12.6 | 9.0% | 0.373 | 0.1 |       64 | 16.7% |  20.0% | 2.1× | 8.5% |   0.0781 |
|       OK |   35 |   37.2 | 5.7% | 0.320 | 0.1 |       34 | 0.0% |      - |    - | 5.9% |   0.0000 |
| DEGRADED |   61 |  118.1 | 4.9% | 0.291 | 0.1 |       61 | 0.0% |   0.0% |    - | 5.0% |   0.0164 |
|      ALL |  163 |   57.4 | 6.8% | 0.331 | 0.1 |      159 | 9.1% |  16.7% | 2.4× | 6.5% |   0.0377 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   14.9 | 37.5% | 0.566 | 0.6 |        5 | 0.0% |      - |    - | 20.0% |   0.0000 |
|       OK |    7 |   37.0 | 42.9% | 0.540 | 0.4 |        6 | 50.0% | 100.0% | 3.0× | 20.0% |   0.1667 |
| DEGRADED |   13 |  129.1 | 0.0% | 0.389 | 0.0 |       13 |    - |   0.0% |    - | 0.0% |   0.1538 |
|      ALL |   28 |   73.4 | 21.4% | 0.477 | 0.3 |       24 | 33.3% |  33.3% | 2.7× | 9.5% |   0.1250 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   14.9 | 0.0% | 0.584 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    7 |   37.0 | 0.0% | 0.478 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |  129.1 | 0.0% | 0.346 | 0.0 |       13 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   28 |   73.4 | 0.0% | 0.447 | 0.0 |       24 |    - |      - |    - | 0.0% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   14.9 | 0.0% | 0.535 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    7 |   37.0 | 0.0% | 0.376 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |  129.1 | 0.0% | 0.248 | 0.0 |       13 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   28 |   73.4 | 0.0% | 0.362 | 0.0 |       24 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available