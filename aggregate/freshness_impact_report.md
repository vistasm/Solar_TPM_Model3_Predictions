# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-09-13 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (72.2%) is 55.5% HIGHER than DEGRADED (16.7%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (9.0%) is 2.4× the overall rate (3.8%) — score distribution shift detected
🟢 **X+**: FRESH precision (14.3%) is 14.3% HIGHER than DEGRADED (0.0%) — fresher data is helping

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   78 |   12.7 | 23.1% | 0.512 | 0.3 |       77 | 72.2% |  36.1% | 1.5× | 12.2% |   0.4675 |
|       OK |   40 |   36.8 | 12.5% | 0.409 | 0.1 |       39 | 40.0% |  40.0% | 3.1× | 8.8% |   0.1282 |
| DEGRADED |   66 |  114.7 | 9.1% | 0.400 | 0.1 |       64 | 16.7% |   6.7% | 0.7× | 10.2% |   0.2344 |
|      ALL |  184 |   54.5 | 15.8% | 0.449 | 0.2 |      180 | 55.2% |  28.6% | 1.8× | 10.5% |   0.3111 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   78 |   12.7 | 9.0% | 0.498 | 0.1 |       77 | 57.1% |  30.8% | 3.4× | 4.7% |   0.1688 |
|       OK |   40 |   36.8 | 0.0% | 0.343 | 0.0 |       39 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   66 |  114.7 | 0.0% | 0.334 | 0.0 |       64 |    - |   0.0% |    - | 0.0% |   0.0469 |
|      ALL |  184 |   54.5 | 3.8% | 0.406 | 0.0 |      180 | 57.1% |  25.0% | 6.4× | 1.8% |   0.0889 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   78 |   12.7 | 9.0% | 0.378 | 0.1 |       77 | 14.3% |  20.0% | 2.2× | 8.3% |   0.0649 |
|       OK |   40 |   36.8 | 5.0% | 0.301 | 0.1 |       39 | 0.0% |      - |    - | 5.1% |   0.0000 |
| DEGRADED |   66 |  114.7 | 4.5% | 0.281 | 0.1 |       64 | 0.0% |   0.0% |    - | 4.8% |   0.0156 |
|      ALL |  184 |   54.5 | 6.5% | 0.326 | 0.1 |      180 | 8.3% |  16.7% | 2.5× | 6.3% |   0.0333 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   16 |   14.0 | 43.8% | 0.519 | 0.6 |       15 | 57.1% |  57.1% | 1.2× | 37.5% |   0.4667 |
|       OK |    8 |   37.5 | 37.5% | 0.437 | 0.4 |        7 | 33.3% | 100.0% | 2.3× | 33.3% |   0.1429 |
| DEGRADED |    6 |   75.4 | 16.7% | 0.330 | 0.2 |        4 | 100.0% | 100.0% | 4.0× | 0.0% |   0.2500 |
|      ALL |   30 |   32.5 | 36.7% | 0.459 | 0.4 |       26 | 54.5% |  66.7% | 1.6× | 29.4% |   0.3462 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   16 |   14.0 | 0.0% | 0.496 | 0.0 |       15 |    - |   0.0% |    - | 0.0% |   0.1333 |
|       OK |    8 |   37.5 | 0.0% | 0.401 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    6 |   75.4 | 0.0% | 0.310 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   30 |   32.5 | 0.0% | 0.434 | 0.0 |       26 |    - |   0.0% |    - | 0.0% |   0.0769 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   16 |   14.0 | 6.2% | 0.456 | 0.1 |       15 | 0.0% |      - |    - | 6.7% |   0.0000 |
|       OK |    8 |   37.5 | 0.0% | 0.244 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    6 |   75.4 | 0.0% | 0.186 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   30 |   32.5 | 3.3% | 0.346 | 0.0 |       26 | 0.0% |      - |    - | 3.9% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available