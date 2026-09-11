# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-09-11 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (72.2%) is 55.5% HIGHER than DEGRADED (16.7%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (9.0%) is 2.3× the overall rate (3.9%) — score distribution shift detected
🟢 **X+**: FRESH precision (14.3%) is 14.3% HIGHER than DEGRADED (0.0%) — fresher data is helping

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   78 |   12.7 | 23.1% | 0.512 | 0.3 |       76 | 72.2% |  36.1% | 1.5× | 12.5% |   0.4737 |
|       OK |   40 |   36.8 | 12.5% | 0.409 | 0.1 |       38 | 40.0% |  40.0% | 3.0× | 9.1% |   0.1316 |
| DEGRADED |   64 |  115.8 | 9.4% | 0.406 | 0.1 |       64 | 16.7% |   6.7% | 0.7× | 10.2% |   0.2344 |
|      ALL |  182 |   54.3 | 15.9% | 0.452 | 0.2 |      178 | 55.2% |  28.6% | 1.8× | 10.7% |   0.3146 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   78 |   12.7 | 9.0% | 0.498 | 0.1 |       76 | 57.1% |  30.8% | 3.3× | 4.8% |   0.1711 |
|       OK |   40 |   36.8 | 0.0% | 0.343 | 0.0 |       38 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   64 |  115.8 | 0.0% | 0.338 | 0.0 |       64 |    - |   0.0% |    - | 0.0% |   0.0469 |
|      ALL |  182 |   54.3 | 3.9% | 0.408 | 0.0 |      178 | 57.1% |  25.0% | 6.4× | 1.8% |   0.0899 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   78 |   12.7 | 9.0% | 0.378 | 0.1 |       76 | 14.3% |  20.0% | 2.2× | 8.5% |   0.0658 |
|       OK |   40 |   36.8 | 5.0% | 0.301 | 0.1 |       38 | 0.0% |      - |    - | 5.3% |   0.0000 |
| DEGRADED |   64 |  115.8 | 4.7% | 0.287 | 0.1 |       64 | 0.0% |   0.0% |    - | 4.8% |   0.0156 |
|      ALL |  182 |   54.3 | 6.6% | 0.329 | 0.1 |      178 | 8.3% |  16.7% | 2.5× | 6.4% |   0.0337 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   16 |   14.0 | 43.8% | 0.519 | 0.6 |       14 | 57.1% |  57.1% | 1.1× | 42.9% |   0.5000 |
|       OK |    8 |   37.5 | 37.5% | 0.437 | 0.4 |        6 | 33.3% | 100.0% | 2.0× | 40.0% |   0.1667 |
| DEGRADED |    5 |   71.1 | 20.0% | 0.417 | 0.2 |        5 | 100.0% | 100.0% | 5.0× | 0.0% |   0.2000 |
|      ALL |   29 |   30.3 | 37.9% | 0.479 | 0.5 |       25 | 54.5% |  66.7% | 1.5× | 31.2% |   0.3600 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   16 |   14.0 | 0.0% | 0.496 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.1429 |
|       OK |    8 |   37.5 | 0.0% | 0.401 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    5 |   71.1 | 0.0% | 0.396 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   29 |   30.3 | 0.0% | 0.453 | 0.0 |       25 |    - |   0.0% |    - | 0.0% |   0.0800 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   16 |   14.0 | 6.2% | 0.456 | 0.1 |       14 | 0.0% |      - |    - | 7.1% |   0.0000 |
|       OK |    8 |   37.5 | 0.0% | 0.244 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    5 |   71.1 | 0.0% | 0.233 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   29 |   30.3 | 3.5% | 0.359 | 0.0 |       25 | 0.0% |      - |    - | 4.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available