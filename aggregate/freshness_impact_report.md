# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-07-10 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (80.0%) is 80.0% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (11.5%) is 2.3× the overall rate (4.9%) — score distribution shift detected
🟢 **X+**: FRESH precision (16.7%) is 16.7% HIGHER than DEGRADED (0.0%) — fresher data is helping

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   52 |   12.1 | 19.2% | 0.502 | 0.2 |       49 | 80.0% |  32.0% | 1.6× | 8.3% |   0.5102 |
|       OK |   26 |   36.7 | 3.9% | 0.401 | 0.0 |       25 | 100.0% |  33.3% | 8.3× | 0.0% |   0.1200 |
| DEGRADED |   44 |  116.4 | 11.4% | 0.423 | 0.1 |       44 | 0.0% |   0.0% |    - | 15.2% |   0.2500 |
|      ALL |  122 |   55.0 | 13.1% | 0.452 | 0.1 |      118 | 56.2% |  23.1% | 1.7× | 8.9% |   0.3305 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   52 |   12.1 | 11.5% | 0.489 | 0.1 |       49 | 66.7% |  36.4% | 3.0× | 5.3% |   0.2245 |
|       OK |   26 |   36.7 | 0.0% | 0.334 | 0.0 |       25 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   44 |  116.4 | 0.0% | 0.351 | 0.0 |       44 |    - |   0.0% |    - | 0.0% |   0.0682 |
|      ALL |  122 |   55.0 | 4.9% | 0.406 | 0.1 |      118 | 66.7% |  28.6% | 5.6× | 1.9% |   0.1186 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   52 |   12.1 | 11.5% | 0.354 | 0.1 |       49 | 16.7% |  20.0% | 1.6× | 11.4% |   0.1020 |
|       OK |   26 |   36.7 | 7.7% | 0.317 | 0.1 |       25 | 0.0% |      - |    - | 8.0% |   0.0000 |
| DEGRADED |   44 |  116.4 | 6.8% | 0.310 | 0.1 |       44 | 0.0% |   0.0% |    - | 7.0% |   0.0227 |
|      ALL |  122 |   55.0 | 9.0% | 0.330 | 0.1 |      118 | 9.1% |  16.7% | 1.8× | 8.9% |   0.0508 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   17 |   10.0 | 41.2% | 0.619 | 0.5 |       14 | 71.4% |  62.5% | 1.2× | 33.3% |   0.5714 |
|       OK |    4 |   35.9 | 0.0% | 0.372 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   10 |  111.0 | 10.0% | 0.515 | 0.1 |       10 | 0.0% |   0.0% |    - | 12.5% |   0.2000 |
|      ALL |   31 |   45.9 | 25.8% | 0.553 | 0.3 |       27 | 62.5% |  50.0% | 1.7× | 17.6% |   0.3704 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   17 |   10.0 | 29.4% | 0.614 | 0.3 |       14 | 60.0% |  50.0% | 1.4× | 25.0% |   0.4286 |
|       OK |    4 |   35.9 | 0.0% | 0.331 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   10 |  111.0 | 0.0% | 0.456 | 0.0 |       10 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   45.9 | 16.1% | 0.527 | 0.2 |       27 | 60.0% |  50.0% | 2.7× | 9.5% |   0.2222 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   17 |   10.0 | 29.4% | 0.576 | 0.3 |       14 | 20.0% |  50.0% | 1.4× | 33.3% |   0.1429 |
|       OK |    4 |   35.9 | 0.0% | 0.283 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   10 |  111.0 | 10.0% | 0.473 | 0.1 |       10 | 0.0% |      - |    - | 10.0% |   0.0000 |
|      ALL |   31 |   45.9 | 19.4% | 0.505 | 0.2 |       27 | 16.7% |  50.0% | 2.2× | 20.0% |   0.0741 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available