# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-05-02 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (100.0%) is 100.0% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (4.5%) is 2.4× the overall rate (1.9%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   22 |   12.8 | 13.6% | 0.489 | 0.1 |       21 | 100.0% |  23.1% | 1.6× | 0.0% |   0.6190 |
|       OK |   12 |   36.0 | 8.3% | 0.439 | 0.1 |       11 | 100.0% |  33.3% | 3.7× | 0.0% |   0.2727 |
| DEGRADED |   19 |  144.8 | 10.5% | 0.379 | 0.1 |       17 | 0.0% |   0.0% |    - | 14.3% |   0.1765 |
|      ALL |   53 |   65.4 | 11.3% | 0.438 | 0.1 |       49 | 66.7% |  21.1% | 1.7× | 6.7% |   0.3878 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   22 |   12.8 | 4.5% | 0.482 | 0.1 |       21 | 100.0% |  25.0% | 5.2× | 0.0% |   0.1905 |
|       OK |   12 |   36.0 | 0.0% | 0.383 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   19 |  144.8 | 0.0% | 0.319 | 0.0 |       17 |    - |   0.0% |    - | 0.0% |   0.0588 |
|      ALL |   53 |   65.4 | 1.9% | 0.402 | 0.0 |       49 | 100.0% |  20.0% | 9.8× | 0.0% |   0.1020 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   22 |   12.8 | 4.5% | 0.265 | 0.1 |       21 | 0.0% |   0.0% |    - | 5.3% |   0.0952 |
|       OK |   12 |   36.0 | 8.3% | 0.335 | 0.1 |       11 | 0.0% |      - |    - | 9.1% |   0.0000 |
| DEGRADED |   19 |  144.8 | 5.3% | 0.229 | 0.1 |       17 | 0.0% |   0.0% |    - | 6.2% |   0.0588 |
|      ALL |   53 |   65.4 | 5.7% | 0.268 | 0.1 |       49 | 0.0% |   0.0% |    - | 6.5% |   0.0612 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   10.4 | 27.3% | 0.560 | 0.3 |       10 | 100.0% |  37.5% | 1.2× | 0.0% |   0.8000 |
|       OK |    4 |   36.2 | 25.0% | 0.482 | 0.2 |        3 | 100.0% | 100.0% | 3.0× | 0.0% |   0.3333 |
| DEGRADED |   15 |  160.5 | 0.0% | 0.367 | 0.0 |       13 |    - |   0.0% |    - | 0.0% |   0.1538 |
|      ALL |   30 |   88.9 | 13.3% | 0.453 | 0.1 |       26 | 100.0% |  36.4% | 2.4× | 0.0% |   0.4231 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   10.4 | 9.1% | 0.577 | 0.1 |       10 | 100.0% |  33.3% | 3.3× | 0.0% |   0.3000 |
|       OK |    4 |   36.2 | 0.0% | 0.393 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   15 |  160.5 | 0.0% | 0.315 | 0.0 |       13 |    - |   0.0% |    - | 0.0% |   0.0769 |
|      ALL |   30 |   88.9 | 3.3% | 0.422 | 0.0 |       26 | 100.0% |  25.0% | 6.5× | 0.0% |   0.1538 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   10.4 | 9.1% | 0.303 | 0.1 |       10 | 0.0% |   0.0% |    - | 11.1% |   0.1000 |
|       OK |    4 |   36.2 | 25.0% | 0.311 | 0.2 |        3 | 0.0% |      - |    - | 33.3% |   0.0000 |
| DEGRADED |   15 |  160.5 | 0.0% | 0.166 | 0.0 |       13 |    - |   0.0% |    - | 0.0% |   0.0769 |
|      ALL |   30 |   88.9 | 6.7% | 0.236 | 0.1 |       26 | 0.0% |   0.0% |    - | 8.3% |   0.0769 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available