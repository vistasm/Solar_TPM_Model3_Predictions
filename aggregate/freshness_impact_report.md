# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-04-02 UTC
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
|    FRESH |   12 |   14.5 | 0.0% | 0.401 | 0.0 |        9 |    - |   0.0% |    - | 0.0% |   0.5556 |
|       OK |    8 |   35.9 | 0.0% | 0.417 | 0.0 |        7 |    - |   0.0% |    - | 0.0% |   0.2857 |
| DEGRADED |    4 |   86.0 | 50.0% | 0.425 | 0.5 |        4 | 0.0% |   0.0% |    - | 66.7% |   0.2500 |
|      ALL |   24 |   33.5 | 8.3% | 0.410 | 0.1 |       20 | 0.0% |   0.0% |    - | 16.7% |   0.4000 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   14.5 | 0.0% | 0.373 | 0.0 |        9 |    - |   0.0% |    - | 0.0% |   0.1111 |
|       OK |    8 |   35.9 | 0.0% | 0.379 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    4 |   86.0 | 0.0% | 0.336 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   24 |   33.5 | 0.0% | 0.369 | 0.0 |       20 |    - |   0.0% |    - | 0.0% |   0.0500 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   14.5 | 0.0% | 0.211 | 0.0 |        9 |    - |   0.0% |    - | 0.0% |   0.1111 |
|       OK |    8 |   35.9 | 0.0% | 0.346 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    4 |   86.0 | 25.0% | 0.467 | 0.2 |        4 | 0.0% |      - |    - | 25.0% |   0.0000 |
|      ALL |   24 |   33.5 | 4.2% | 0.299 | 0.0 |       20 | 0.0% |   0.0% |    - | 5.3% |   0.0500 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   14.5 | 0.0% | 0.401 | 0.0 |        9 |    - |   0.0% |    - | 0.0% |   0.5556 |
|       OK |    8 |   35.9 | 0.0% | 0.417 | 0.0 |        7 |    - |   0.0% |    - | 0.0% |   0.2857 |
| DEGRADED |    4 |   86.0 | 50.0% | 0.425 | 0.5 |        4 | 0.0% |   0.0% |    - | 66.7% |   0.2500 |
|      ALL |   24 |   33.5 | 8.3% | 0.410 | 0.1 |       20 | 0.0% |   0.0% |    - | 16.7% |   0.4000 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   14.5 | 0.0% | 0.373 | 0.0 |        9 |    - |   0.0% |    - | 0.0% |   0.1111 |
|       OK |    8 |   35.9 | 0.0% | 0.379 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    4 |   86.0 | 0.0% | 0.336 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   24 |   33.5 | 0.0% | 0.369 | 0.0 |       20 |    - |   0.0% |    - | 0.0% |   0.0500 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   14.5 | 0.0% | 0.211 | 0.0 |        9 |    - |   0.0% |    - | 0.0% |   0.1111 |
|       OK |    8 |   35.9 | 0.0% | 0.346 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    4 |   86.0 | 25.0% | 0.467 | 0.2 |        4 | 0.0% |      - |    - | 25.0% |   0.0000 |
|      ALL |   24 |   33.5 | 4.2% | 0.299 | 0.0 |       20 | 0.0% |   0.0% |    - | 5.3% |   0.0500 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available