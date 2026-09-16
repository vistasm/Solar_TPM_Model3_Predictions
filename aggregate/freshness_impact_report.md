# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-09-16 UTC
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
|    FRESH |   78 |   12.7 | 23.1% | 0.512 | 0.3 |       78 | 72.2% |  36.1% | 1.6× | 11.9% |   0.4615 |
|       OK |   40 |   36.8 | 12.5% | 0.409 | 0.1 |       40 | 40.0% |  40.0% | 3.2× | 8.6% |   0.1250 |
| DEGRADED |   67 |  115.4 | 9.0% | 0.397 | 0.1 |       65 | 16.7% |   6.7% | 0.7× | 10.0% |   0.2308 |
|      ALL |  185 |   55.1 | 15.7% | 0.448 | 0.2 |      183 | 55.2% |  28.6% | 1.8× | 10.2% |   0.3060 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   78 |   12.7 | 9.0% | 0.498 | 0.1 |       78 | 57.1% |  30.8% | 3.4× | 4.6% |   0.1667 |
|       OK |   40 |   36.8 | 0.0% | 0.343 | 0.0 |       40 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   67 |  115.4 | 0.0% | 0.330 | 0.0 |       65 |    - |   0.0% |    - | 0.0% |   0.0462 |
|      ALL |  185 |   55.1 | 3.8% | 0.404 | 0.0 |      183 | 57.1% |  25.0% | 6.5× | 1.8% |   0.0874 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   78 |   12.7 | 9.0% | 0.378 | 0.1 |       78 | 14.3% |  20.0% | 2.2× | 8.2% |   0.0641 |
|       OK |   40 |   36.8 | 5.0% | 0.301 | 0.1 |       40 | 0.0% |      - |    - | 5.0% |   0.0000 |
| DEGRADED |   67 |  115.4 | 4.5% | 0.278 | 0.0 |       65 | 0.0% |   0.0% |    - | 4.7% |   0.0154 |
|      ALL |  185 |   55.1 | 6.5% | 0.325 | 0.1 |      183 | 8.3% |  16.7% | 2.5× | 6.2% |   0.0328 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |   13.4 | 46.7% | 0.520 | 0.6 |       15 | 57.1% |  57.1% | 1.2× | 37.5% |   0.4667 |
|       OK |    7 |   36.2 | 42.9% | 0.443 | 0.4 |        7 | 33.3% | 100.0% | 2.3× | 33.3% |   0.1429 |
| DEGRADED |    6 |   88.1 | 16.7% | 0.306 | 0.2 |        4 | 100.0% | 100.0% | 4.0× | 0.0% |   0.2500 |
|      ALL |   28 |   35.1 | 39.3% | 0.455 | 0.5 |       26 | 54.5% |  66.7% | 1.6× | 29.4% |   0.3462 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |   13.4 | 0.0% | 0.489 | 0.0 |       15 |    - |   0.0% |    - | 0.0% |   0.1333 |
|       OK |    7 |   36.2 | 0.0% | 0.386 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    6 |   88.1 | 0.0% | 0.269 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   28 |   35.1 | 0.0% | 0.416 | 0.0 |       26 |    - |   0.0% |    - | 0.0% |   0.0769 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |   13.4 | 6.7% | 0.472 | 0.1 |       15 | 0.0% |      - |    - | 6.7% |   0.0000 |
|       OK |    7 |   36.2 | 0.0% | 0.248 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    6 |   88.1 | 0.0% | 0.146 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   28 |   35.1 | 3.6% | 0.346 | 0.0 |       26 | 0.0% |      - |    - | 3.9% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available