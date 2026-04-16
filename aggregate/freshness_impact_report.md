# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-04-16 UTC
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
| DEGRADED |   11 |   96.4 | 18.2% | 0.362 | 0.2 |        7 | 0.0% |   0.0% |    - | 33.3% |   0.1429 |
|      ALL |   38 |   43.9 | 7.9% | 0.400 | 0.1 |       34 | 33.3% |   8.3% | 0.9× | 9.1% |   0.3529 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   16 |   13.5 | 0.0% | 0.375 | 0.0 |       16 |    - |   0.0% |    - | 0.0% |   0.1250 |
|       OK |   11 |   35.7 | 0.0% | 0.387 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   11 |   96.4 | 0.0% | 0.300 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   38 |   43.9 | 0.0% | 0.357 | 0.0 |       34 |    - |   0.0% |    - | 0.0% |   0.0588 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   16 |   13.5 | 6.2% | 0.232 | 0.1 |       16 | 0.0% |   0.0% |    - | 6.7% |   0.0625 |
|       OK |   11 |   35.7 | 9.1% | 0.357 | 0.1 |       11 | 0.0% |      - |    - | 9.1% |   0.0000 |
| DEGRADED |   11 |   96.4 | 9.1% | 0.278 | 0.1 |        7 | 0.0% |      - |    - | 14.3% |   0.0000 |
|      ALL |   38 |   43.9 | 7.9% | 0.281 | 0.1 |       34 | 0.0% |   0.0% |    - | 9.1% |   0.0294 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   13.1 | 0.0% | 0.396 | 0.0 |       13 |    - |   0.0% |    - | 0.0% |   0.5385 |
|       OK |    8 |   35.3 | 12.5% | 0.430 | 0.1 |        8 | 100.0% |  50.0% | 4.0× | 0.0% |   0.2500 |
| DEGRADED |   10 |   99.5 | 20.0% | 0.366 | 0.2 |        6 | 0.0% |      - |    - | 33.3% |   0.0000 |
|      ALL |   31 |   46.7 | 9.7% | 0.395 | 0.1 |       27 | 33.3% |  11.1% | 1.0× | 11.1% |   0.3333 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   13.1 | 0.0% | 0.388 | 0.0 |       13 |    - |   0.0% |    - | 0.0% |   0.1538 |
|       OK |    8 |   35.3 | 0.0% | 0.400 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   10 |   99.5 | 0.0% | 0.306 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   46.7 | 0.0% | 0.365 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   13.1 | 7.7% | 0.238 | 0.1 |       13 | 0.0% |   0.0% |    - | 8.3% |   0.0769 |
|       OK |    8 |   35.3 | 12.5% | 0.292 | 0.1 |        8 | 0.0% |      - |    - | 12.5% |   0.0000 |
| DEGRADED |   10 |   99.5 | 10.0% | 0.298 | 0.1 |        6 | 0.0% |      - |    - | 16.7% |   0.0000 |
|      ALL |   31 |   46.7 | 9.7% | 0.271 | 0.1 |       27 | 0.0% |   0.0% |    - | 11.5% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available