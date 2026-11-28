# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-11-28 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (66.7%) is 28.2% HIGHER than DEGRADED (38.5%) — fresher data is helping
🟢 **X+**: FRESH precision (12.5%) is 12.5% HIGHER than DEGRADED (0.0%) — fresher data is helping

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   88 |   12.6 | 23.9% | 0.521 | 0.3 |       87 | 66.7% |  36.8% | 1.5× | 14.3% |   0.4368 |
|       OK |   48 |   36.5 | 14.6% | 0.432 | 0.1 |       47 | 42.9% |  42.9% | 2.9× | 10.0% |   0.1489 |
| DEGRADED |  128 |  115.6 | 10.2% | 0.394 | 0.1 |      126 | 38.5% |  20.8% | 2.0× | 7.8% |   0.1905 |
|      ALL |  264 |   66.9 | 15.5% | 0.443 | 0.2 |      260 | 53.7% |  31.9% | 2.0× | 10.0% |   0.2654 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   88 |   12.6 | 11.4% | 0.503 | 0.1 |       87 | 40.0% |  30.8% | 2.7× | 8.1% |   0.1494 |
|       OK |   48 |   36.5 | 4.2% | 0.371 | 0.0 |       47 | 0.0% |      - |    - | 4.3% |   0.0000 |
| DEGRADED |  128 |  115.6 | 3.9% | 0.336 | 0.0 |      126 | 40.0% |  40.0% | 10.1× | 2.5% |   0.0397 |
|      ALL |  264 |   66.9 | 6.4% | 0.398 | 0.1 |      260 | 35.3% |  33.3% | 5.1× | 4.5% |   0.0692 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   88 |   12.6 | 9.1% | 0.390 | 0.1 |       87 | 12.5% |  20.0% | 2.2× | 8.5% |   0.0575 |
|       OK |   48 |   36.5 | 4.2% | 0.335 | 0.0 |       47 | 0.0% |      - |    - | 4.3% |   0.0000 |
| DEGRADED |  128 |  115.6 | 3.9% | 0.268 | 0.0 |      126 | 0.0% |   0.0% |    - | 4.0% |   0.0079 |
|      ALL |  264 |   66.9 | 5.7% | 0.321 | 0.1 |      260 | 6.7% |  16.7% | 2.9× | 5.5% |   0.0231 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   11.7 | 33.3% | 0.649 | 0.3 |        8 | 33.3% |  50.0% | 1.3× | 33.3% |   0.2500 |
|       OK |    7 |   34.7 | 28.6% | 0.538 | 0.3 |        6 | 50.0% |  50.0% | 1.5× | 25.0% |   0.3333 |
| DEGRADED |   15 |  124.6 | 6.7% | 0.255 | 0.1 |       13 | 100.0% |  50.0% | 6.5× | 0.0% |   0.1538 |
|      ALL |   31 |   71.5 | 19.4% | 0.433 | 0.2 |       27 | 50.0% |  50.0% | 2.2× | 14.3% |   0.2222 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   11.7 | 33.3% | 0.599 | 0.3 |        8 | 0.0% |      - |    - | 37.5% |   0.0000 |
|       OK |    7 |   34.7 | 28.6% | 0.512 | 0.3 |        6 | 0.0% |      - |    - | 33.3% |   0.0000 |
| DEGRADED |   15 |  124.6 | 6.7% | 0.184 | 0.1 |       13 | 0.0% |      - |    - | 7.7% |   0.0000 |
|      ALL |   31 |   71.5 | 19.4% | 0.378 | 0.2 |       27 | 0.0% |      - |    - | 22.2% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   11.7 | 11.1% | 0.543 | 0.1 |        8 | 0.0% |      - |    - | 12.5% |   0.0000 |
|       OK |    7 |   34.7 | 0.0% | 0.451 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   15 |  124.6 | 0.0% | 0.169 | 0.0 |       13 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   71.5 | 3.2% | 0.341 | 0.0 |       27 | 0.0% |      - |    - | 3.7% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available