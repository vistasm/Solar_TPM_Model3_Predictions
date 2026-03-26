# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-03-26 UTC
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
|    FRESH |    7 |   15.1 | 0.0% | 0.431 | 0.0 |        6 |    - |   0.0% |    - | 0.0% |   0.5000 |
|       OK |    6 |   35.6 | 0.0% | 0.420 | 0.0 |        4 |    - |   0.0% |    - | 0.0% |   0.2500 |
| DEGRADED |    4 |   86.0 | 50.0% | 0.425 | 0.5 |        3 | 0.0% |   0.0% |    - | 50.0% |   0.3333 |
|      ALL |   17 |   39.0 | 11.8% | 0.426 | 0.1 |       13 | 0.0% |   0.0% |    - | 12.5% |   0.3846 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    7 |   15.1 | 0.0% | 0.363 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    6 |   35.6 | 0.0% | 0.349 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    4 |   86.0 | 0.0% | 0.336 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   17 |   39.0 | 0.0% | 0.351 | 0.0 |       13 |    - |      - |    - | 0.0% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    7 |   15.1 | 0.0% | 0.174 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    6 |   35.6 | 0.0% | 0.368 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    4 |   86.0 | 25.0% | 0.467 | 0.2 |        3 | 0.0% |      - |    - | 33.3% |   0.0000 |
|      ALL |   17 |   39.0 | 5.9% | 0.311 | 0.1 |       13 | 0.0% |      - |    - | 7.7% |   0.0000 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    7 |   15.1 | 0.0% | 0.431 | 0.0 |        6 |    - |   0.0% |    - | 0.0% |   0.5000 |
|       OK |    6 |   35.6 | 0.0% | 0.420 | 0.0 |        4 |    - |   0.0% |    - | 0.0% |   0.2500 |
| DEGRADED |    4 |   86.0 | 50.0% | 0.425 | 0.5 |        3 | 0.0% |   0.0% |    - | 50.0% |   0.3333 |
|      ALL |   17 |   39.0 | 11.8% | 0.426 | 0.1 |       13 | 0.0% |   0.0% |    - | 12.5% |   0.3846 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    7 |   15.1 | 0.0% | 0.363 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    6 |   35.6 | 0.0% | 0.349 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    4 |   86.0 | 0.0% | 0.336 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   17 |   39.0 | 0.0% | 0.351 | 0.0 |       13 |    - |      - |    - | 0.0% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    7 |   15.1 | 0.0% | 0.174 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    6 |   35.6 | 0.0% | 0.368 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    4 |   86.0 | 25.0% | 0.467 | 0.2 |        3 | 0.0% |      - |    - | 33.3% |   0.0000 |
|      ALL |   17 |   39.0 | 5.9% | 0.311 | 0.1 |       13 | 0.0% |      - |    - | 7.7% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available