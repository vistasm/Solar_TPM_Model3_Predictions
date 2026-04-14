# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-04-14 UTC
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
|       OK |   11 |   35.7 | 9.1% | 0.438 | 0.1 |       10 | 100.0% |  33.3% | 3.3× | 0.0% |   0.3000 |
| DEGRADED |    9 |   83.9 | 22.2% | 0.380 | 0.2 |        6 | 0.0% |   0.0% |    - | 40.0% |   0.1667 |
|      ALL |   36 |   37.9 | 8.3% | 0.407 | 0.1 |       32 | 33.3% |   8.3% | 0.9× | 10.0% |   0.3750 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   16 |   13.5 | 0.0% | 0.375 | 0.0 |       16 |    - |   0.0% |    - | 0.0% |   0.1250 |
|       OK |   11 |   35.7 | 0.0% | 0.387 | 0.0 |       10 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    9 |   83.9 | 0.0% | 0.315 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   36 |   37.9 | 0.0% | 0.364 | 0.0 |       32 |    - |   0.0% |    - | 0.0% |   0.0625 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   16 |   13.5 | 6.2% | 0.232 | 0.1 |       16 | 0.0% |   0.0% |    - | 6.7% |   0.0625 |
|       OK |   11 |   35.7 | 9.1% | 0.357 | 0.1 |       10 | 0.0% |      - |    - | 10.0% |   0.0000 |
| DEGRADED |    9 |   83.9 | 11.1% | 0.325 | 0.1 |        6 | 0.0% |      - |    - | 16.7% |   0.0000 |
|      ALL |   36 |   37.9 | 8.3% | 0.293 | 0.1 |       32 | 0.0% |   0.0% |    - | 9.7% |   0.0312 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   13.6 | 0.0% | 0.394 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.5714 |
|       OK |    9 |   35.0 | 11.1% | 0.419 | 0.1 |        8 | 100.0% |  33.3% | 2.7× | 0.0% |   0.3750 |
| DEGRADED |    8 |   86.2 | 25.0% | 0.387 | 0.2 |        5 | 0.0% |      - |    - | 40.0% |   0.0000 |
|      ALL |   31 |   38.5 | 9.7% | 0.399 | 0.1 |       27 | 33.3% |   9.1% | 0.8× | 12.5% |   0.4074 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   13.6 | 0.0% | 0.385 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.1429 |
|       OK |    9 |   35.0 | 0.0% | 0.381 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    8 |   86.2 | 0.0% | 0.325 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   38.5 | 0.0% | 0.368 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   13.6 | 7.1% | 0.226 | 0.1 |       14 | 0.0% |   0.0% |    - | 7.7% |   0.0714 |
|       OK |    9 |   35.0 | 11.1% | 0.274 | 0.1 |        8 | 0.0% |      - |    - | 12.5% |   0.0000 |
| DEGRADED |    8 |   86.2 | 12.5% | 0.355 | 0.1 |        5 | 0.0% |      - |    - | 20.0% |   0.0000 |
|      ALL |   31 |   38.5 | 9.7% | 0.273 | 0.1 |       27 | 0.0% |   0.0% |    - | 11.5% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available