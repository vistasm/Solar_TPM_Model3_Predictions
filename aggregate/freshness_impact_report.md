# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-05-22 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (100.0%) is 100.0% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (3.5%) is 2.5× the overall rate (1.4%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   29 |   12.6 | 10.3% | 0.460 | 0.1 |       28 | 100.0% |  20.0% | 1.9× | 0.0% |   0.5357 |
|       OK |   18 |   35.6 | 5.6% | 0.385 | 0.1 |       17 | 100.0% |  33.3% | 5.7× | 0.0% |   0.1765 |
| DEGRADED |   26 |  123.5 | 7.7% | 0.371 | 0.1 |       24 | 0.0% |   0.0% |    - | 10.5% |   0.2083 |
|      ALL |   73 |   57.8 | 8.2% | 0.410 | 0.1 |       69 | 66.7% |  17.4% | 2.0× | 4.3% |   0.3333 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   29 |   12.6 | 3.5% | 0.439 | 0.0 |       28 | 100.0% |  25.0% | 7.0× | 0.0% |   0.1429 |
|       OK |   18 |   35.6 | 0.0% | 0.324 | 0.0 |       17 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   26 |  123.5 | 0.0% | 0.304 | 0.0 |       24 |    - |   0.0% |    - | 0.0% |   0.0833 |
|      ALL |   73 |   57.8 | 1.4% | 0.363 | 0.0 |       69 | 100.0% |  16.7% | 11.5× | 0.0% |   0.0870 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   29 |   12.6 | 3.5% | 0.251 | 0.0 |       28 | 0.0% |   0.0% |    - | 3.9% |   0.0714 |
|       OK |   18 |   35.6 | 5.6% | 0.259 | 0.1 |       17 | 0.0% |      - |    - | 5.9% |   0.0000 |
| DEGRADED |   26 |  123.5 | 3.9% | 0.221 | 0.0 |       24 | 0.0% |   0.0% |    - | 4.3% |   0.0417 |
|      ALL |   73 |   57.8 | 4.1% | 0.242 | 0.0 |       69 | 0.0% |   0.0% |    - | 4.5% |   0.0435 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   11.4 | 23.1% | 0.533 | 0.2 |       12 | 100.0% |  42.9% | 1.7× | 0.0% |   0.5833 |
|       OK |    7 |   35.4 | 0.0% | 0.302 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   11 |  113.7 | 0.0% | 0.390 | 0.0 |        9 |    - |   0.0% |    - | 0.0% |   0.4444 |
|      ALL |   31 |   53.2 | 9.7% | 0.430 | 0.1 |       27 | 100.0% |  27.3% | 2.5× | 0.0% |   0.4074 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   11.4 | 7.7% | 0.519 | 0.1 |       12 | 100.0% |  50.0% | 6.0× | 0.0% |   0.1667 |
|       OK |    7 |   35.4 | 0.0% | 0.225 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   11 |  113.7 | 0.0% | 0.305 | 0.0 |        9 |    - |   0.0% |    - | 0.0% |   0.2222 |
|      ALL |   31 |   53.2 | 3.2% | 0.377 | 0.0 |       27 | 100.0% |  25.0% | 6.8× | 0.0% |   0.1481 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   11.4 | 0.0% | 0.274 | 0.0 |       12 |    - |   0.0% |    - | 0.0% |   0.0833 |
|       OK |    7 |   35.4 | 0.0% | 0.105 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   11 |  113.7 | 0.0% | 0.213 | 0.0 |        9 |    - |   0.0% |    - | 0.0% |   0.1111 |
|      ALL |   31 |   53.2 | 0.0% | 0.214 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available