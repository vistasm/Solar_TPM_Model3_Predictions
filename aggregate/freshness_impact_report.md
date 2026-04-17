# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-04-17 UTC
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
| DEGRADED |   12 |  104.1 | 16.7% | 0.372 | 0.2 |        8 | 0.0% |   0.0% |    - | 28.6% |   0.1250 |
|      ALL |   39 |   47.6 | 7.7% | 0.402 | 0.1 |       35 | 33.3% |   8.3% | 1.0× | 8.7% |   0.3429 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   16 |   13.5 | 0.0% | 0.375 | 0.0 |       16 |    - |   0.0% |    - | 0.0% |   0.1250 |
|       OK |   11 |   35.7 | 0.0% | 0.387 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   12 |  104.1 | 0.0% | 0.309 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   39 |   47.6 | 0.0% | 0.358 | 0.0 |       35 |    - |   0.0% |    - | 0.0% |   0.0571 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   16 |   13.5 | 6.2% | 0.232 | 0.1 |       16 | 0.0% |   0.0% |    - | 6.7% |   0.0625 |
|       OK |   11 |   35.7 | 9.1% | 0.357 | 0.1 |       11 | 0.0% |      - |    - | 9.1% |   0.0000 |
| DEGRADED |   12 |  104.1 | 8.3% | 0.265 | 0.1 |        8 | 0.0% |      - |    - | 12.5% |   0.0000 |
|      ALL |   39 |   47.6 | 7.7% | 0.277 | 0.1 |       35 | 0.0% |   0.0% |    - | 8.8% |   0.0286 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   13.1 | 0.0% | 0.384 | 0.0 |       12 |    - |   0.0% |    - | 0.0% |   0.5000 |
|       OK |    8 |   35.3 | 12.5% | 0.430 | 0.1 |        8 | 100.0% |  50.0% | 4.0× | 0.0% |   0.2500 |
| DEGRADED |   11 |  107.6 | 18.2% | 0.376 | 0.2 |        7 | 0.0% |      - |    - | 28.6% |   0.0000 |
|      ALL |   31 |   52.4 | 9.7% | 0.393 | 0.1 |       27 | 33.3% |  12.5% | 1.1× | 10.5% |   0.2963 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   13.1 | 0.0% | 0.380 | 0.0 |       12 |    - |   0.0% |    - | 0.0% |   0.1667 |
|       OK |    8 |   35.3 | 0.0% | 0.400 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   11 |  107.6 | 0.0% | 0.316 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   52.4 | 0.0% | 0.362 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   13.1 | 8.3% | 0.237 | 0.1 |       12 | 0.0% |   0.0% |    - | 9.1% |   0.0833 |
|       OK |    8 |   35.3 | 12.5% | 0.292 | 0.1 |        8 | 0.0% |      - |    - | 12.5% |   0.0000 |
| DEGRADED |   11 |  107.6 | 9.1% | 0.281 | 0.1 |        7 | 0.0% |      - |    - | 14.3% |   0.0000 |
|      ALL |   31 |   52.4 | 9.7% | 0.267 | 0.1 |       27 | 0.0% |   0.0% |    - | 11.5% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available