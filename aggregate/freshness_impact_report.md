# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-08-02 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (81.8%) is 81.8% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (11.3%) is 2.3× the overall rate (4.8%) — score distribution shift detected
🟢 **X+**: FRESH precision (16.7%) is 16.7% HIGHER than DEGRADED (0.0%) — fresher data is helping

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   62 |   12.4 | 17.7% | 0.510 | 0.2 |       61 | 81.8% |  31.0% | 1.7× | 6.2% |   0.4754 |
|       OK |   32 |   36.7 | 6.2% | 0.402 | 0.1 |       31 | 100.0% |  25.0% | 7.8× | 0.0% |   0.1290 |
| DEGRADED |   51 |  111.9 | 9.8% | 0.417 | 0.1 |       49 | 0.0% |   0.0% |    - | 13.9% |   0.2653 |
|      ALL |  145 |   52.7 | 12.4% | 0.454 | 0.1 |      141 | 58.8% |  21.7% | 1.8× | 7.4% |   0.3262 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   62 |   12.4 | 11.3% | 0.498 | 0.1 |       61 | 57.1% |  36.4% | 3.2× | 6.0% |   0.1803 |
|       OK |   32 |   36.7 | 0.0% | 0.329 | 0.0 |       31 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   51 |  111.9 | 0.0% | 0.343 | 0.0 |       49 |    - |   0.0% |    - | 0.0% |   0.0612 |
|      ALL |  145 |   52.7 | 4.8% | 0.406 | 0.1 |      141 | 57.1% |  28.6% | 5.8× | 2.4% |   0.0993 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   62 |   12.4 | 9.7% | 0.357 | 0.1 |       61 | 16.7% |  20.0% | 2.0× | 8.9% |   0.0820 |
|       OK |   32 |   36.7 | 6.2% | 0.315 | 0.1 |       31 | 0.0% |      - |    - | 6.5% |   0.0000 |
| DEGRADED |   51 |  111.9 | 5.9% | 0.302 | 0.1 |       49 | 0.0% |   0.0% |    - | 6.2% |   0.0204 |
|      ALL |  145 |   52.7 | 7.6% | 0.329 | 0.1 |      141 | 9.1% |  16.7% | 2.1× | 7.4% |   0.0426 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   17 |   12.5 | 29.4% | 0.621 | 0.4 |       16 | 80.0% |  57.1% | 1.8× | 11.1% |   0.4375 |
|       OK |    7 |   34.7 | 14.3% | 0.423 | 0.1 |        6 |    - |   0.0% |    - | 0.0% |   0.1667 |
| DEGRADED |    7 |   83.1 | 0.0% | 0.379 | 0.0 |        5 |    - |   0.0% |    - | 0.0% |   0.4000 |
|      ALL |   31 |   33.4 | 19.4% | 0.521 | 0.3 |       27 | 80.0% |  40.0% | 2.2× | 5.9% |   0.3704 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   17 |   12.5 | 29.4% | 0.615 | 0.3 |       16 | 60.0% | 100.0% | 3.2× | 15.4% |   0.1875 |
|       OK |    7 |   34.7 | 0.0% | 0.352 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    7 |   83.1 | 0.0% | 0.290 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   33.4 | 16.1% | 0.482 | 0.2 |       27 | 60.0% | 100.0% | 5.4× | 8.3% |   0.1111 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   17 |   12.5 | 23.5% | 0.485 | 0.2 |       16 | 25.0% | 100.0% | 4.0× | 20.0% |   0.0625 |
|       OK |    7 |   34.7 | 0.0% | 0.352 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    7 |   83.1 | 0.0% | 0.254 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   33.4 | 12.9% | 0.403 | 0.1 |       27 | 25.0% | 100.0% | 6.8× | 11.5% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available