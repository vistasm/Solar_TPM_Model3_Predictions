# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-09-18 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (72.2%) is 55.5% HIGHER than DEGRADED (16.7%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (9.0%) is 2.4× the overall rate (3.7%) — score distribution shift detected
🟢 **X+**: FRESH precision (14.3%) is 14.3% HIGHER than DEGRADED (0.0%) — fresher data is helping

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   78 |   12.7 | 23.1% | 0.512 | 0.3 |       78 | 72.2% |  36.1% | 1.6× | 11.9% |   0.4615 |
|       OK |   40 |   36.8 | 12.5% | 0.409 | 0.1 |       40 | 40.0% |  40.0% | 3.2× | 8.6% |   0.1250 |
| DEGRADED |   69 |  117.9 | 8.7% | 0.395 | 0.1 |       66 | 16.7% |   6.7% | 0.7× | 9.8% |   0.2273 |
|      ALL |  187 |   56.7 | 15.5% | 0.447 | 0.2 |      184 | 55.2% |  28.6% | 1.8× | 10.2% |   0.3043 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   78 |   12.7 | 9.0% | 0.498 | 0.1 |       78 | 57.1% |  30.8% | 3.4× | 4.6% |   0.1667 |
|       OK |   40 |   36.8 | 0.0% | 0.343 | 0.0 |       40 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   69 |  117.9 | 0.0% | 0.325 | 0.0 |       66 |    - |   0.0% |    - | 0.0% |   0.0455 |
|      ALL |  187 |   56.7 | 3.7% | 0.401 | 0.0 |      184 | 57.1% |  25.0% | 6.6× | 1.8% |   0.0870 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   78 |   12.7 | 9.0% | 0.378 | 0.1 |       78 | 14.3% |  20.0% | 2.2× | 8.2% |   0.0641 |
|       OK |   40 |   36.8 | 5.0% | 0.301 | 0.1 |       40 | 0.0% |      - |    - | 5.0% |   0.0000 |
| DEGRADED |   69 |  117.9 | 4.3% | 0.274 | 0.0 |       66 | 0.0% |   0.0% |    - | 4.6% |   0.0152 |
|      ALL |  187 |   56.7 | 6.4% | 0.323 | 0.1 |      184 | 8.3% |  16.7% | 2.6× | 6.2% |   0.0326 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   13.4 | 42.9% | 0.513 | 0.6 |       14 | 66.7% |  57.1% | 1.3× | 28.6% |   0.5000 |
|       OK |    7 |   36.2 | 42.9% | 0.443 | 0.4 |        7 | 33.3% | 100.0% | 2.3× | 33.3% |   0.1429 |
| DEGRADED |    8 |  116.1 | 12.5% | 0.308 | 0.1 |        5 | 100.0% | 100.0% | 5.0× | 0.0% |   0.2000 |
|      ALL |   29 |   47.3 | 34.5% | 0.439 | 0.4 |       26 | 60.0% |  66.7% | 1.7× | 23.5% |   0.3462 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   13.4 | 0.0% | 0.475 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.1429 |
|       OK |    7 |   36.2 | 0.0% | 0.386 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    8 |  116.1 | 0.0% | 0.241 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   29 |   47.3 | 0.0% | 0.389 | 0.0 |       26 |    - |   0.0% |    - | 0.0% |   0.0769 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   13.4 | 7.1% | 0.473 | 0.1 |       14 | 0.0% |      - |    - | 7.1% |   0.0000 |
|       OK |    7 |   36.2 | 0.0% | 0.248 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    8 |  116.1 | 0.0% | 0.151 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   29 |   47.3 | 3.5% | 0.330 | 0.0 |       26 | 0.0% |      - |    - | 3.9% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available