# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-09-20 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (72.2%) is 55.5% HIGHER than DEGRADED (16.7%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (8.9%) is 2.4× the overall rate (3.7%) — score distribution shift detected
🟢 **X+**: FRESH precision (14.3%) is 14.3% HIGHER than DEGRADED (0.0%) — fresher data is helping

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   79 |   12.7 | 22.8% | 0.507 | 0.3 |       78 | 72.2% |  36.1% | 1.6× | 11.9% |   0.4615 |
|       OK |   40 |   36.8 | 12.5% | 0.409 | 0.1 |       40 | 40.0% |  40.0% | 3.2× | 8.6% |   0.1250 |
| DEGRADED |   70 |  119.6 | 8.6% | 0.393 | 0.1 |       67 | 16.7% |   6.7% | 0.7× | 9.6% |   0.2239 |
|      ALL |  189 |   57.4 | 15.3% | 0.444 | 0.2 |      185 | 55.2% |  28.6% | 1.8× | 10.1% |   0.3027 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   79 |   12.7 | 8.9% | 0.492 | 0.1 |       78 | 57.1% |  30.8% | 3.4× | 4.6% |   0.1667 |
|       OK |   40 |   36.8 | 0.0% | 0.343 | 0.0 |       40 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   70 |  119.6 | 0.0% | 0.323 | 0.0 |       67 |    - |   0.0% |    - | 0.0% |   0.0448 |
|      ALL |  189 |   57.4 | 3.7% | 0.398 | 0.0 |      185 | 57.1% |  25.0% | 6.6× | 1.8% |   0.0865 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   79 |   12.7 | 8.9% | 0.373 | 0.1 |       78 | 14.3% |  20.0% | 2.2× | 8.2% |   0.0641 |
|       OK |   40 |   36.8 | 5.0% | 0.301 | 0.1 |       40 | 0.0% |      - |    - | 5.0% |   0.0000 |
| DEGRADED |   70 |  119.6 | 4.3% | 0.271 | 0.0 |       67 | 0.0% |   0.0% |    - | 4.5% |   0.0149 |
|      ALL |  189 |   57.4 | 6.3% | 0.320 | 0.1 |      185 | 8.3% |  16.7% | 2.6× | 6.2% |   0.0324 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   13.5 | 35.7% | 0.474 | 0.4 |       13 | 60.0% |  50.0% | 1.3× | 28.6% |   0.4615 |
|       OK |    6 |   36.1 | 33.3% | 0.396 | 0.3 |        6 | 0.0% |      - |    - | 33.3% |   0.0000 |
| DEGRADED |    9 |  129.5 | 11.1% | 0.304 | 0.1 |        6 | 100.0% | 100.0% | 6.0× | 0.0% |   0.1667 |
|      ALL |   29 |   54.2 | 27.6% | 0.405 | 0.3 |       25 | 50.0% |  57.1% | 1.8× | 22.2% |   0.2800 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   13.5 | 0.0% | 0.428 | 0.0 |       13 |    - |   0.0% |    - | 0.0% |   0.0769 |
|       OK |    6 |   36.1 | 0.0% | 0.340 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    9 |  129.5 | 0.0% | 0.229 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   29 |   54.2 | 0.0% | 0.348 | 0.0 |       25 |    - |   0.0% |    - | 0.0% |   0.0400 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   13.5 | 7.1% | 0.408 | 0.1 |       13 | 0.0% |      - |    - | 7.7% |   0.0000 |
|       OK |    6 |   36.1 | 0.0% | 0.221 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    9 |  129.5 | 0.0% | 0.140 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   29 |   54.2 | 3.5% | 0.286 | 0.0 |       25 | 0.0% |      - |    - | 4.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available