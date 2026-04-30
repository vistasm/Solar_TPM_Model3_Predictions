# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-04-30 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (100.0%) is 100.0% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (4.5%) is 2.3× the overall rate (2.0%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   22 |   12.8 | 13.6% | 0.489 | 0.1 |       19 | 100.0% |  27.3% | 1.7× | 0.0% |   0.5789 |
|       OK |   12 |   36.0 | 8.3% | 0.439 | 0.1 |       11 | 100.0% |  33.3% | 3.7× | 0.0% |   0.2727 |
| DEGRADED |   17 |  153.0 | 11.8% | 0.373 | 0.1 |       17 | 0.0% |   0.0% |    - | 14.3% |   0.1765 |
|      ALL |   51 |   65.0 | 11.8% | 0.438 | 0.1 |       47 | 66.7% |  23.5% | 1.8× | 6.7% |   0.3617 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   22 |   12.8 | 4.5% | 0.482 | 0.1 |       19 | 100.0% |  25.0% | 4.8× | 0.0% |   0.2105 |
|       OK |   12 |   36.0 | 0.0% | 0.383 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   17 |  153.0 | 0.0% | 0.325 | 0.0 |       17 |    - |   0.0% |    - | 0.0% |   0.0588 |
|      ALL |   51 |   65.0 | 2.0% | 0.407 | 0.0 |       47 | 100.0% |  20.0% | 9.4× | 0.0% |   0.1064 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   22 |   12.8 | 4.5% | 0.265 | 0.1 |       19 | 0.0% |   0.0% |    - | 5.9% |   0.1053 |
|       OK |   12 |   36.0 | 8.3% | 0.335 | 0.1 |       11 | 0.0% |      - |    - | 9.1% |   0.0000 |
| DEGRADED |   17 |  153.0 | 5.9% | 0.245 | 0.1 |       17 | 0.0% |   0.0% |    - | 6.2% |   0.0588 |
|      ALL |   51 |   65.0 | 5.9% | 0.275 | 0.1 |       47 | 0.0% |   0.0% |    - | 6.8% |   0.0638 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   11.1 | 25.0% | 0.532 | 0.2 |        9 | 100.0% |  50.0% | 1.5× | 0.0% |   0.6667 |
|       OK |    5 |   34.2 | 20.0% | 0.453 | 0.2 |        4 | 100.0% | 100.0% | 4.0× | 0.0% |   0.2500 |
| DEGRADED |   13 |  173.6 | 0.0% | 0.357 | 0.0 |       13 |    - |   0.0% |    - | 0.0% |   0.1538 |
|      ALL |   30 |   85.4 | 13.3% | 0.443 | 0.1 |       26 | 100.0% |  44.4% | 2.9× | 0.0% |   0.3462 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   11.1 | 8.3% | 0.546 | 0.1 |        9 | 100.0% |  33.3% | 3.0× | 0.0% |   0.3333 |
|       OK |    5 |   34.2 | 0.0% | 0.388 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |  173.6 | 0.0% | 0.322 | 0.0 |       13 |    - |   0.0% |    - | 0.0% |   0.0769 |
|      ALL |   30 |   85.4 | 3.3% | 0.422 | 0.0 |       26 | 100.0% |  25.0% | 6.5× | 0.0% |   0.1538 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   11.1 | 8.3% | 0.283 | 0.1 |        9 | 0.0% |   0.0% |    - | 12.5% |   0.1111 |
|       OK |    5 |   34.2 | 20.0% | 0.271 | 0.2 |        4 | 0.0% |      - |    - | 25.0% |   0.0000 |
| DEGRADED |   13 |  173.6 | 0.0% | 0.177 | 0.0 |       13 |    - |   0.0% |    - | 0.0% |   0.0769 |
|      ALL |   30 |   85.4 | 6.7% | 0.235 | 0.1 |       26 | 0.0% |   0.0% |    - | 8.3% |   0.0769 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available