# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-04-15 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

✅ No anomalies detected. Insufficient data or metrics within normal range.

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   16 |   13.5 | 0.0% | 0.400 | 0.0 |       16 |    - |   0.0% |    - | 0.0% |   0.5000 |
|       OK |   11 |   35.7 | 9.1% | 0.438 | 0.1 |       11 | 100.0% |  33.3% | 3.7× | 0.0% |   0.2727 |
| DEGRADED |   10 |   89.6 | 20.0% | 0.360 | 0.2 |        6 | 0.0% |   0.0% |    - | 40.0% |   0.1667 |
|      ALL |   37 |   40.7 | 8.1% | 0.401 | 0.1 |       33 | 33.3% |   8.3% | 0.9× | 9.5% |   0.3636 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   16 |   13.5 | 0.0% | 0.375 | 0.0 |       16 |    - |   0.0% |    - | 0.0% |   0.1250 |
|       OK |   11 |   35.7 | 0.0% | 0.387 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   10 |   89.6 | 0.0% | 0.295 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   37 |   40.7 | 0.0% | 0.357 | 0.0 |       33 |    - |   0.0% |    - | 0.0% |   0.0606 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   16 |   13.5 | 6.2% | 0.232 | 0.1 |       16 | 0.0% |   0.0% |    - | 6.7% |   0.0625 |
|       OK |   11 |   35.7 | 9.1% | 0.357 | 0.1 |       11 | 0.0% |      - |    - | 9.1% |   0.0000 |
| DEGRADED |   10 |   89.6 | 10.0% | 0.296 | 0.1 |        6 | 0.0% |      - |    - | 16.7% |   0.0000 |
|      ALL |   37 |   40.7 | 8.1% | 0.286 | 0.1 |       33 | 0.0% |   0.0% |    - | 9.4% |   0.0303 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   13.6 | 0.0% | 0.394 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.5714 |
|       OK |    8 |   35.3 | 12.5% | 0.430 | 0.1 |        8 | 100.0% |  50.0% | 4.0× | 0.0% |   0.2500 |
| DEGRADED |    9 |   92.3 | 22.2% | 0.363 | 0.2 |        5 | 0.0% |      - |    - | 40.0% |   0.0000 |
|      ALL |   31 |   42.0 | 9.7% | 0.395 | 0.1 |       27 | 33.3% |  10.0% | 0.9× | 11.8% |   0.3704 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   13.6 | 0.0% | 0.385 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.1429 |
|       OK |    8 |   35.3 | 0.0% | 0.400 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    9 |   92.3 | 0.0% | 0.301 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   42.0 | 0.0% | 0.364 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   13.6 | 7.1% | 0.226 | 0.1 |       14 | 0.0% |   0.0% |    - | 7.7% |   0.0714 |
|       OK |    8 |   35.3 | 12.5% | 0.292 | 0.1 |        8 | 0.0% |      - |    - | 12.5% |   0.0000 |
| DEGRADED |    9 |   92.3 | 11.1% | 0.320 | 0.1 |        5 | 0.0% |      - |    - | 20.0% |   0.0000 |
|      ALL |   31 |   42.0 | 9.7% | 0.270 | 0.1 |       27 | 0.0% |   0.0% |    - | 11.5% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available