# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-06-25 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (75.0%) is 75.0% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (2.4%) is 2.6× the overall rate (0.9%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   42 |   12.9 | 9.5% | 0.445 | 0.1 |       41 | 75.0% |  15.8% | 1.6× | 4.5% |   0.4634 |
|       OK |   25 |   37.2 | 4.0% | 0.396 | 0.0 |       24 | 100.0% |  33.3% | 8.0× | 0.0% |   0.1250 |
| DEGRADED |   40 |  113.9 | 10.0% | 0.398 | 0.1 |       38 | 0.0% |   0.0% |    - | 14.3% |   0.2632 |
|      ALL |  107 |   56.3 | 8.4% | 0.416 | 0.1 |      103 | 44.4% |  12.5% | 1.4× | 7.0% |   0.3107 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   42 |   12.9 | 2.4% | 0.426 | 0.0 |       41 | 100.0% |  16.7% | 6.8× | 0.0% |   0.1463 |
|       OK |   25 |   37.2 | 0.0% | 0.323 | 0.0 |       24 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   40 |  113.9 | 0.0% | 0.323 | 0.0 |       38 |    - |   0.0% |    - | 0.0% |   0.0789 |
|      ALL |  107 |   56.3 | 0.9% | 0.363 | 0.0 |      103 | 100.0% |  11.1% | 11.4× | 0.0% |   0.0874 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   42 |   12.9 | 4.8% | 0.284 | 0.1 |       41 | 0.0% |   0.0% |    - | 5.3% |   0.0732 |
|       OK |   25 |   37.2 | 8.0% | 0.305 | 0.1 |       24 | 0.0% |      - |    - | 8.3% |   0.0000 |
| DEGRADED |   40 |  113.9 | 7.5% | 0.288 | 0.1 |       38 | 0.0% |   0.0% |    - | 5.4% |   0.0263 |
|      ALL |  107 |   56.3 | 6.5% | 0.290 | 0.1 |      103 | 0.0% |   0.0% |    - | 6.1% |   0.0388 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   12.9 | 8.3% | 0.420 | 0.1 |       11 | 0.0% |   0.0% |    - | 14.3% |   0.3636 |
|       OK |    6 |   41.2 | 0.0% | 0.402 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |   98.3 | 7.7% | 0.437 | 0.1 |       11 | 0.0% |   0.0% |    - | 14.3% |   0.3636 |
|      ALL |   31 |   54.2 | 6.5% | 0.423 | 0.1 |       27 | 0.0% |   0.0% |    - | 10.5% |   0.2963 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   12.9 | 0.0% | 0.417 | 0.0 |       11 |    - |   0.0% |    - | 0.0% |   0.1818 |
|       OK |    6 |   41.2 | 0.0% | 0.295 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |   98.3 | 0.0% | 0.345 | 0.0 |       11 |    - |   0.0% |    - | 0.0% |   0.0909 |
|      ALL |   31 |   54.2 | 0.0% | 0.363 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.1111 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   12.9 | 8.3% | 0.381 | 0.1 |       11 | 0.0% |   0.0% |    - | 10.0% |   0.0909 |
|       OK |    6 |   41.2 | 16.7% | 0.382 | 0.2 |        5 | 0.0% |      - |    - | 20.0% |   0.0000 |
| DEGRADED |   13 |   98.3 | 15.4% | 0.415 | 0.1 |       11 | 0.0% |      - |    - | 9.1% |   0.0000 |
|      ALL |   31 |   54.2 | 12.9% | 0.396 | 0.1 |       27 | 0.0% |   0.0% |    - | 11.5% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available