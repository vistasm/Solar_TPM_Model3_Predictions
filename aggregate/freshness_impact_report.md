# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-08-06 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (81.8%) is 81.8% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (11.3%) is 2.4× the overall rate (4.7%) — score distribution shift detected
🟢 **X+**: FRESH precision (16.7%) is 16.7% HIGHER than DEGRADED (0.0%) — fresher data is helping

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   62 |   12.4 | 17.7% | 0.510 | 0.2 |       62 | 81.8% |  31.0% | 1.8× | 6.1% |   0.4677 |
|       OK |   32 |   36.7 | 6.2% | 0.402 | 0.1 |       32 | 50.0% |  25.0% | 4.0× | 3.6% |   0.1250 |
| DEGRADED |   55 |  112.5 | 9.1% | 0.417 | 0.1 |       51 | 0.0% |   0.0% |    - | 13.5% |   0.2745 |
|      ALL |  149 |   54.6 | 12.1% | 0.453 | 0.1 |      145 | 55.6% |  21.3% | 1.7× | 8.2% |   0.3241 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   62 |   12.4 | 11.3% | 0.498 | 0.1 |       62 | 57.1% |  36.4% | 3.2× | 5.9% |   0.1774 |
|       OK |   32 |   36.7 | 0.0% | 0.329 | 0.0 |       32 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   55 |  112.5 | 0.0% | 0.348 | 0.0 |       51 |    - |   0.0% |    - | 0.0% |   0.0588 |
|      ALL |  149 |   54.6 | 4.7% | 0.407 | 0.1 |      145 | 57.1% |  28.6% | 5.9× | 2.3% |   0.0966 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   62 |   12.4 | 9.7% | 0.357 | 0.1 |       62 | 16.7% |  20.0% | 2.1× | 8.8% |   0.0806 |
|       OK |   32 |   36.7 | 6.2% | 0.315 | 0.1 |       32 | 0.0% |      - |    - | 6.2% |   0.0000 |
| DEGRADED |   55 |  112.5 | 5.5% | 0.298 | 0.1 |       51 | 0.0% |   0.0% |    - | 6.0% |   0.0196 |
|      ALL |  149 |   54.6 | 7.4% | 0.327 | 0.1 |      145 | 9.1% |  16.7% | 2.2× | 7.2% |   0.0414 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   14.6 | 7.7% | 0.511 | 0.1 |       13 | 100.0% |  25.0% | 3.2× | 0.0% |   0.3077 |
|       OK |    7 |   34.7 | 14.3% | 0.423 | 0.1 |        7 | 0.0% |   0.0% |    - | 16.7% |   0.1429 |
| DEGRADED |   11 |   96.7 | 0.0% | 0.394 | 0.0 |        7 |    - |   0.0% |    - | 0.0% |   0.4286 |
|      ALL |   31 |   48.3 | 6.5% | 0.450 | 0.1 |       27 | 50.0% |  12.5% | 1.7× | 5.3% |   0.2963 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   14.6 | 7.7% | 0.505 | 0.1 |       13 | 0.0% |      - |    - | 7.7% |   0.0000 |
|       OK |    7 |   34.7 | 0.0% | 0.352 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   11 |   96.7 | 0.0% | 0.336 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   48.3 | 3.2% | 0.410 | 0.0 |       27 | 0.0% |      - |    - | 3.7% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   14.6 | 0.0% | 0.339 | 0.0 |       13 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    7 |   34.7 | 0.0% | 0.352 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   11 |   96.7 | 0.0% | 0.253 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   48.3 | 0.0% | 0.311 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available