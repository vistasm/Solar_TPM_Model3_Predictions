# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-04-06 UTC
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
|    FRESH |   15 |   13.1 | 0.0% | 0.410 | 0.0 |       12 |    - |   0.0% |    - | 0.0% |   0.5000 |
|       OK |    9 |   35.3 | 0.0% | 0.414 | 0.0 |        8 |    - |   0.0% |    - | 0.0% |   0.2500 |
| DEGRADED |    4 |   86.0 | 50.0% | 0.425 | 0.5 |        4 | 0.0% |   0.0% |    - | 66.7% |   0.2500 |
|      ALL |   28 |   30.6 | 7.1% | 0.413 | 0.1 |       24 | 0.0% |   0.0% |    - | 13.3% |   0.3750 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |   13.1 | 0.0% | 0.393 | 0.0 |       12 |    - |   0.0% |    - | 0.0% |   0.0833 |
|       OK |    9 |   35.3 | 0.0% | 0.386 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    4 |   86.0 | 0.0% | 0.336 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   28 |   30.6 | 0.0% | 0.382 | 0.0 |       24 |    - |   0.0% |    - | 0.0% |   0.0417 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |   13.1 | 6.7% | 0.245 | 0.1 |       12 |    - |   0.0% |    - | 0.0% |   0.0833 |
|       OK |    9 |   35.3 | 0.0% | 0.323 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    4 |   86.0 | 25.0% | 0.467 | 0.2 |        4 | 0.0% |      - |    - | 25.0% |   0.0000 |
|      ALL |   28 |   30.6 | 7.1% | 0.301 | 0.1 |       24 | 0.0% |   0.0% |    - | 4.3% |   0.0417 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |   13.1 | 0.0% | 0.410 | 0.0 |       12 |    - |   0.0% |    - | 0.0% |   0.5000 |
|       OK |    9 |   35.3 | 0.0% | 0.414 | 0.0 |        8 |    - |   0.0% |    - | 0.0% |   0.2500 |
| DEGRADED |    4 |   86.0 | 50.0% | 0.425 | 0.5 |        4 | 0.0% |   0.0% |    - | 66.7% |   0.2500 |
|      ALL |   28 |   30.6 | 7.1% | 0.413 | 0.1 |       24 | 0.0% |   0.0% |    - | 13.3% |   0.3750 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |   13.1 | 0.0% | 0.393 | 0.0 |       12 |    - |   0.0% |    - | 0.0% |   0.0833 |
|       OK |    9 |   35.3 | 0.0% | 0.386 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    4 |   86.0 | 0.0% | 0.336 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   28 |   30.6 | 0.0% | 0.382 | 0.0 |       24 |    - |   0.0% |    - | 0.0% |   0.0417 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |   13.1 | 6.7% | 0.245 | 0.1 |       12 |    - |   0.0% |    - | 0.0% |   0.0833 |
|       OK |    9 |   35.3 | 0.0% | 0.323 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    4 |   86.0 | 25.0% | 0.467 | 0.2 |        4 | 0.0% |      - |    - | 25.0% |   0.0000 |
|      ALL |   28 |   30.6 | 7.1% | 0.301 | 0.1 |       24 | 0.0% |   0.0% |    - | 4.3% |   0.0417 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available