# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-08-27 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (71.4%) is 71.4% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (10.0%) is 2.4× the overall rate (4.2%) — score distribution shift detected
🟢 **X+**: FRESH precision (16.7%) is 16.7% HIGHER than DEGRADED (0.0%) — fresher data is helping

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   70 |   12.5 | 24.3% | 0.528 | 0.3 |       67 | 71.4% |  32.3% | 1.5× | 11.1% |   0.4627 |
|       OK |   35 |   37.2 | 11.4% | 0.418 | 0.1 |       35 | 50.0% |  40.0% | 3.5× | 6.7% |   0.1429 |
| DEGRADED |   62 |  117.3 | 9.7% | 0.410 | 0.1 |       61 | 0.0% |   0.0% |    - | 10.6% |   0.2295 |
|      ALL |  167 |   56.6 | 16.2% | 0.461 | 0.2 |      163 | 52.2% |  24.0% | 1.7× | 9.7% |   0.3067 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   70 |   12.5 | 10.0% | 0.520 | 0.1 |       67 | 57.1% |  33.3% | 3.2× | 5.5% |   0.1791 |
|       OK |   35 |   37.2 | 0.0% | 0.352 | 0.0 |       35 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   62 |  117.3 | 0.0% | 0.342 | 0.0 |       61 |    - |   0.0% |    - | 0.0% |   0.0492 |
|      ALL |  167 |   56.6 | 4.2% | 0.419 | 0.0 |      163 | 57.1% |  26.7% | 6.2× | 2.0% |   0.0920 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   70 |   12.5 | 8.6% | 0.374 | 0.1 |       67 | 16.7% |  20.0% | 2.2× | 8.1% |   0.0746 |
|       OK |   35 |   37.2 | 5.7% | 0.320 | 0.1 |       35 | 0.0% |      - |    - | 5.7% |   0.0000 |
| DEGRADED |   62 |  117.3 | 4.8% | 0.293 | 0.1 |       61 | 0.0% |   0.0% |    - | 5.0% |   0.0164 |
|      ALL |  167 |   56.6 | 6.6% | 0.333 | 0.1 |      163 | 9.1% |  16.7% | 2.5× | 6.4% |   0.0368 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   13.3 | 66.7% | 0.648 | 0.9 |        6 | 33.3% |  50.0% | 1.0× | 50.0% |   0.3333 |
|       OK |    6 |   36.8 | 50.0% | 0.563 | 0.5 |        6 | 33.3% | 100.0% | 2.0× | 40.0% |   0.1667 |
| DEGRADED |   13 |  129.5 | 7.7% | 0.403 | 0.1 |       12 |    - |   0.0% |    - | 0.0% |   0.0833 |
|      ALL |   28 |   72.3 | 35.7% | 0.516 | 0.4 |       24 | 33.3% |  50.0% | 2.0× | 20.0% |   0.1667 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   13.3 | 0.0% | 0.674 | 0.0 |        6 |    - |   0.0% |    - | 0.0% |   0.1667 |
|       OK |    6 |   36.8 | 0.0% | 0.515 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |  129.5 | 0.0% | 0.370 | 0.0 |       12 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   28 |   72.3 | 0.0% | 0.499 | 0.0 |       24 |    - |   0.0% |    - | 0.0% |   0.0417 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   13.3 | 0.0% | 0.498 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    6 |   36.8 | 0.0% | 0.417 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |  129.5 | 0.0% | 0.266 | 0.0 |       12 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   28 |   72.3 | 0.0% | 0.373 | 0.0 |       24 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available