# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-05-03 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (100.0%) is 100.0% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (4.3%) is 2.4× the overall rate (1.8%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   23 |   12.7 | 13.0% | 0.486 | 0.1 |       22 | 100.0% |  23.1% | 1.7× | 0.0% |   0.5909 |
|       OK |   12 |   36.0 | 8.3% | 0.439 | 0.1 |       11 | 100.0% |  33.3% | 3.7× | 0.0% |   0.2727 |
| DEGRADED |   19 |  144.8 | 10.5% | 0.379 | 0.1 |       17 | 0.0% |   0.0% |    - | 14.3% |   0.1765 |
|      ALL |   54 |   64.4 | 11.1% | 0.438 | 0.1 |       50 | 66.7% |  21.1% | 1.8× | 6.5% |   0.3800 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   23 |   12.7 | 4.3% | 0.477 | 0.0 |       22 | 100.0% |  25.0% | 5.5× | 0.0% |   0.1818 |
|       OK |   12 |   36.0 | 0.0% | 0.383 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   19 |  144.8 | 0.0% | 0.319 | 0.0 |       17 |    - |   0.0% |    - | 0.0% |   0.0588 |
|      ALL |   54 |   64.4 | 1.8% | 0.401 | 0.0 |       50 | 100.0% |  20.0% | 10.0× | 0.0% |   0.1000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   23 |   12.7 | 4.3% | 0.259 | 0.0 |       22 | 0.0% |   0.0% |    - | 5.0% |   0.0909 |
|       OK |   12 |   36.0 | 8.3% | 0.335 | 0.1 |       11 | 0.0% |      - |    - | 9.1% |   0.0000 |
| DEGRADED |   19 |  144.8 | 5.3% | 0.229 | 0.1 |       17 | 0.0% |   0.0% |    - | 6.2% |   0.0588 |
|      ALL |   54 |   64.4 | 5.6% | 0.265 | 0.1 |       50 | 0.0% |   0.0% |    - | 6.4% |   0.0600 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   10.8 | 27.3% | 0.579 | 0.3 |       10 | 100.0% |  42.9% | 1.4× | 0.0% |   0.7000 |
|       OK |    4 |   36.2 | 25.0% | 0.482 | 0.2 |        3 | 100.0% | 100.0% | 3.0× | 0.0% |   0.3333 |
| DEGRADED |   15 |  160.5 | 0.0% | 0.367 | 0.0 |       13 |    - |   0.0% |    - | 0.0% |   0.1538 |
|      ALL |   30 |   89.1 | 13.3% | 0.460 | 0.1 |       26 | 100.0% |  40.0% | 2.6× | 0.0% |   0.3846 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   10.8 | 9.1% | 0.591 | 0.1 |       10 | 100.0% |  33.3% | 3.3× | 0.0% |   0.3000 |
|       OK |    4 |   36.2 | 0.0% | 0.393 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   15 |  160.5 | 0.0% | 0.315 | 0.0 |       13 |    - |   0.0% |    - | 0.0% |   0.0769 |
|      ALL |   30 |   89.1 | 3.3% | 0.427 | 0.0 |       26 | 100.0% |  25.0% | 6.5× | 0.0% |   0.1538 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   10.8 | 9.1% | 0.310 | 0.1 |       10 | 0.0% |   0.0% |    - | 11.1% |   0.1000 |
|       OK |    4 |   36.2 | 25.0% | 0.311 | 0.2 |        3 | 0.0% |      - |    - | 33.3% |   0.0000 |
| DEGRADED |   15 |  160.5 | 0.0% | 0.166 | 0.0 |       13 |    - |   0.0% |    - | 0.0% |   0.0769 |
|      ALL |   30 |   89.1 | 6.7% | 0.238 | 0.1 |       26 | 0.0% |   0.0% |    - | 8.3% |   0.0769 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available