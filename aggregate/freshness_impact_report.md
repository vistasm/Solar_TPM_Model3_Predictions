# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-04-10 UTC
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
|    FRESH |   16 |   13.5 | 0.0% | 0.400 | 0.0 |       15 |    - |   0.0% |    - | 0.0% |   0.5333 |
|       OK |   10 |   34.8 | 10.0% | 0.454 | 0.1 |        9 |    - |   0.0% |    - | 0.0% |   0.2222 |
| DEGRADED |    6 |   79.5 | 33.3% | 0.379 | 0.3 |        4 | 0.0% |   0.0% |    - | 66.7% |   0.2500 |
|      ALL |   32 |   32.5 | 9.4% | 0.413 | 0.1 |       28 | 0.0% |   0.0% |    - | 11.8% |   0.3929 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   16 |   13.5 | 0.0% | 0.375 | 0.0 |       15 |    - |   0.0% |    - | 0.0% |   0.1333 |
|       OK |   10 |   34.8 | 0.0% | 0.401 | 0.0 |        9 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    6 |   79.5 | 0.0% | 0.305 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   32 |   32.5 | 0.0% | 0.370 | 0.0 |       28 |    - |   0.0% |    - | 0.0% |   0.0714 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   16 |   13.5 | 6.2% | 0.232 | 0.1 |       15 | 0.0% |   0.0% |    - | 7.1% |   0.0667 |
|       OK |   10 |   34.8 | 10.0% | 0.388 | 0.1 |        9 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    6 |   79.5 | 16.7% | 0.344 | 0.2 |        4 | 0.0% |      - |    - | 25.0% |   0.0000 |
|      ALL |   32 |   32.5 | 9.4% | 0.302 | 0.1 |       28 | 0.0% |   0.0% |    - | 7.4% |   0.0357 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   16 |   13.5 | 0.0% | 0.400 | 0.0 |       15 |    - |   0.0% |    - | 0.0% |   0.5333 |
|       OK |    9 |   34.7 | 11.1% | 0.443 | 0.1 |        8 |    - |   0.0% |    - | 0.0% |   0.2500 |
| DEGRADED |    6 |   79.5 | 33.3% | 0.379 | 0.3 |        4 | 0.0% |   0.0% |    - | 66.7% |   0.2500 |
|      ALL |   31 |   32.4 | 9.7% | 0.409 | 0.1 |       27 | 0.0% |   0.0% |    - | 12.5% |   0.4074 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   16 |   13.5 | 0.0% | 0.375 | 0.0 |       15 |    - |   0.0% |    - | 0.0% |   0.1333 |
|       OK |    9 |   34.7 | 0.0% | 0.387 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    6 |   79.5 | 0.0% | 0.305 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   32.4 | 0.0% | 0.365 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   16 |   13.5 | 6.2% | 0.232 | 0.1 |       15 | 0.0% |   0.0% |    - | 7.1% |   0.0667 |
|       OK |    9 |   34.7 | 11.1% | 0.349 | 0.1 |        8 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    6 |   79.5 | 16.7% | 0.344 | 0.2 |        4 | 0.0% |      - |    - | 25.0% |   0.0000 |
|      ALL |   31 |   32.4 | 9.7% | 0.287 | 0.1 |       27 | 0.0% |   0.0% |    - | 7.7% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available