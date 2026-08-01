# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-08-01 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (81.8%) is 81.8% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (11.3%) is 2.3× the overall rate (4.9%) — score distribution shift detected
🟢 **X+**: FRESH precision (16.7%) is 16.7% HIGHER than DEGRADED (0.0%) — fresher data is helping

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   62 |   12.4 | 17.7% | 0.510 | 0.2 |       61 | 81.8% |  31.0% | 1.7× | 6.2% |   0.4754 |
|       OK |   32 |   36.7 | 6.2% | 0.402 | 0.1 |       30 | 100.0% |  25.0% | 7.5× | 0.0% |   0.1333 |
| DEGRADED |   50 |  112.9 | 10.0% | 0.415 | 0.1 |       49 | 0.0% |   0.0% |    - | 13.9% |   0.2653 |
|      ALL |  144 |   52.7 | 12.5% | 0.453 | 0.1 |      140 | 58.8% |  21.7% | 1.8× | 7.4% |   0.3286 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   62 |   12.4 | 11.3% | 0.498 | 0.1 |       61 | 57.1% |  36.4% | 3.2× | 6.0% |   0.1803 |
|       OK |   32 |   36.7 | 0.0% | 0.329 | 0.0 |       30 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   50 |  112.9 | 0.0% | 0.338 | 0.0 |       49 |    - |   0.0% |    - | 0.0% |   0.0612 |
|      ALL |  144 |   52.7 | 4.9% | 0.405 | 0.1 |      140 | 57.1% |  28.6% | 5.7× | 2.4% |   0.1000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   62 |   12.4 | 9.7% | 0.357 | 0.1 |       61 | 16.7% |  20.0% | 2.0× | 8.9% |   0.0820 |
|       OK |   32 |   36.7 | 6.2% | 0.315 | 0.1 |       30 | 0.0% |      - |    - | 6.7% |   0.0000 |
| DEGRADED |   50 |  112.9 | 6.0% | 0.300 | 0.1 |       49 | 0.0% |   0.0% |    - | 6.2% |   0.0204 |
|      ALL |  144 |   52.7 | 7.6% | 0.328 | 0.1 |      140 | 9.1% |  16.7% | 2.1× | 7.5% |   0.0429 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   18 |   12.0 | 33.3% | 0.639 | 0.4 |       17 | 83.3% |  62.5% | 1.8× | 11.1% |   0.4706 |
|       OK |    7 |   34.7 | 14.3% | 0.423 | 0.1 |        5 |    - |   0.0% |    - | 0.0% |   0.2000 |
| DEGRADED |    6 |   86.8 | 0.0% | 0.358 | 0.0 |        5 |    - |   0.0% |    - | 0.0% |   0.4000 |
|      ALL |   31 |   31.6 | 22.6% | 0.536 | 0.3 |       27 | 83.3% |  45.5% | 2.0× | 6.2% |   0.4074 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   18 |   12.0 | 33.3% | 0.634 | 0.3 |       17 | 50.0% | 100.0% | 2.8× | 21.4% |   0.1765 |
|       OK |    7 |   34.7 | 0.0% | 0.352 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    6 |   86.8 | 0.0% | 0.241 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   31.6 | 19.4% | 0.494 | 0.2 |       27 | 50.0% | 100.0% | 4.5× | 12.5% |   0.1111 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   18 |   12.0 | 22.2% | 0.509 | 0.2 |       17 | 25.0% | 100.0% | 4.2× | 18.8% |   0.0588 |
|       OK |    7 |   34.7 | 0.0% | 0.352 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    6 |   86.8 | 0.0% | 0.229 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   31.6 | 12.9% | 0.419 | 0.1 |       27 | 25.0% | 100.0% | 6.8× | 11.5% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available