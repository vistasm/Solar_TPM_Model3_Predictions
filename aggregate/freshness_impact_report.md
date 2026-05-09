# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-05-09 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (100.0%) is 100.0% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (4.0%) is 2.4× the overall rate (1.7%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   25 |   12.5 | 12.0% | 0.475 | 0.1 |       24 | 100.0% |  21.4% | 1.7× | 0.0% |   0.5833 |
|       OK |   14 |   35.6 | 7.1% | 0.413 | 0.1 |       13 | 100.0% |  33.3% | 4.3× | 0.0% |   0.2308 |
| DEGRADED |   21 |  137.1 | 9.5% | 0.366 | 0.1 |       19 | 0.0% |   0.0% |    - | 12.5% |   0.1579 |
|      ALL |   60 |   61.5 | 10.0% | 0.422 | 0.1 |       56 | 66.7% |  20.0% | 1.9× | 5.6% |   0.3571 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   25 |   12.5 | 4.0% | 0.460 | 0.0 |       24 | 100.0% |  25.0% | 6.0× | 0.0% |   0.1667 |
|       OK |   14 |   35.6 | 0.0% | 0.358 | 0.0 |       13 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   21 |  137.1 | 0.0% | 0.307 | 0.0 |       19 |    - |   0.0% |    - | 0.0% |   0.0526 |
|      ALL |   60 |   61.5 | 1.7% | 0.383 | 0.0 |       56 | 100.0% |  20.0% | 11.2× | 0.0% |   0.0893 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   25 |   12.5 | 4.0% | 0.254 | 0.0 |       24 | 0.0% |   0.0% |    - | 4.5% |   0.0833 |
|       OK |   14 |   35.6 | 7.1% | 0.315 | 0.1 |       13 | 0.0% |      - |    - | 7.7% |   0.0000 |
| DEGRADED |   21 |  137.1 | 4.8% | 0.212 | 0.1 |       19 | 0.0% |   0.0% |    - | 5.6% |   0.0526 |
|      ALL |   60 |   61.5 | 5.0% | 0.253 | 0.1 |       56 | 0.0% |   0.0% |    - | 5.7% |   0.0536 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   11.5 | 30.0% | 0.572 | 0.3 |        9 | 100.0% |  50.0% | 1.5× | 0.0% |   0.6667 |
|       OK |    5 |   36.1 | 20.0% | 0.412 | 0.2 |        4 | 100.0% | 100.0% | 4.0× | 0.0% |   0.2500 |
| DEGRADED |   15 |  160.2 | 0.0% | 0.361 | 0.0 |       13 |    - |   0.0% |    - | 0.0% |   0.1538 |
|      ALL |   30 |   90.0 | 13.3% | 0.440 | 0.1 |       26 | 100.0% |  44.4% | 2.9× | 0.0% |   0.3462 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   11.5 | 10.0% | 0.561 | 0.1 |        9 | 100.0% |  50.0% | 4.5× | 0.0% |   0.2222 |
|       OK |    5 |   36.1 | 0.0% | 0.308 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   15 |  160.2 | 0.0% | 0.308 | 0.0 |       13 |    - |   0.0% |    - | 0.0% |   0.0769 |
|      ALL |   30 |   90.0 | 3.3% | 0.392 | 0.0 |       26 | 100.0% |  33.3% | 8.7× | 0.0% |   0.1154 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   11.5 | 0.0% | 0.267 | 0.0 |        9 |    - |   0.0% |    - | 0.0% |   0.1111 |
|       OK |    5 |   36.1 | 20.0% | 0.301 | 0.2 |        4 | 0.0% |      - |    - | 25.0% |   0.0000 |
| DEGRADED |   15 |  160.2 | 0.0% | 0.159 | 0.0 |       13 |    - |   0.0% |    - | 0.0% |   0.0769 |
|      ALL |   30 |   90.0 | 3.3% | 0.219 | 0.0 |       26 | 0.0% |   0.0% |    - | 4.2% |   0.0769 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available