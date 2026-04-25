# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-04-25 UTC
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
|    FRESH |   18 |   12.9 | 11.1% | 0.442 | 0.1 |       16 |    - |   0.0% |    - | 0.0% |   0.5000 |
|       OK |   11 |   35.7 | 9.1% | 0.438 | 0.1 |       11 | 100.0% |  33.3% | 3.7× | 0.0% |   0.2727 |
| DEGRADED |   17 |  153.0 | 11.8% | 0.373 | 0.1 |       15 | 0.0% |   0.0% |    - | 14.3% |   0.0667 |
|      ALL |   46 |   70.1 | 10.9% | 0.415 | 0.1 |       42 | 33.3% |   8.3% | 1.2× | 6.7% |   0.2857 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   18 |   12.9 | 0.0% | 0.428 | 0.0 |       16 |    - |   0.0% |    - | 0.0% |   0.1250 |
|       OK |   11 |   35.7 | 0.0% | 0.387 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   17 |  153.0 | 0.0% | 0.325 | 0.0 |       15 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   46 |   70.1 | 0.0% | 0.380 | 0.0 |       42 |    - |   0.0% |    - | 0.0% |   0.0476 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   18 |   12.9 | 5.6% | 0.259 | 0.1 |       16 | 0.0% |   0.0% |    - | 6.7% |   0.0625 |
|       OK |   11 |   35.7 | 9.1% | 0.357 | 0.1 |       11 | 0.0% |      - |    - | 9.1% |   0.0000 |
| DEGRADED |   17 |  153.0 | 5.9% | 0.245 | 0.1 |       15 | 0.0% |      - |    - | 6.7% |   0.0000 |
|      ALL |   46 |   70.1 | 6.5% | 0.277 | 0.1 |       42 | 0.0% |   0.0% |    - | 7.3% |   0.0238 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   11.5 | 18.2% | 0.450 | 0.2 |        9 |    - |   0.0% |    - | 0.0% |   0.5556 |
|       OK |    6 |   34.7 | 16.7% | 0.451 | 0.2 |        6 | 100.0% |  50.0% | 3.0× | 0.0% |   0.3333 |
| DEGRADED |   13 |  173.6 | 0.0% | 0.357 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   30 |   86.4 | 10.0% | 0.410 | 0.1 |       26 | 100.0% |  14.3% | 3.7× | 0.0% |   0.2692 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   11.5 | 0.0% | 0.470 | 0.0 |        9 |    - |   0.0% |    - | 0.0% |   0.2222 |
|       OK |    6 |   34.7 | 0.0% | 0.426 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |  173.6 | 0.0% | 0.322 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   30 |   86.4 | 0.0% | 0.397 | 0.0 |       26 |    - |   0.0% |    - | 0.0% |   0.0769 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   11.5 | 9.1% | 0.312 | 0.1 |        9 | 0.0% |   0.0% |    - | 12.5% |   0.1111 |
|       OK |    6 |   34.7 | 16.7% | 0.371 | 0.2 |        6 | 0.0% |      - |    - | 16.7% |   0.0000 |
| DEGRADED |   13 |  173.6 | 0.0% | 0.177 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   30 |   86.4 | 6.7% | 0.265 | 0.1 |       26 | 0.0% |   0.0% |    - | 8.0% |   0.0385 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available