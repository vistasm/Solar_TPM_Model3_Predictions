# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-06-09 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (100.0%) is 100.0% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (2.9%) is 2.6× the overall rate (1.1%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   35 |   13.1 | 8.6% | 0.446 | 0.1 |       33 | 100.0% |  18.8% | 2.1× | 0.0% |   0.4848 |
|       OK |   22 |   36.9 | 4.5% | 0.407 | 0.1 |       21 | 100.0% |  33.3% | 7.0× | 0.0% |   0.1429 |
| DEGRADED |   34 |  118.1 | 11.8% | 0.396 | 0.1 |       33 | 0.0% |   0.0% |    - | 16.7% |   0.2727 |
|      ALL |   91 |   58.1 | 8.8% | 0.418 | 0.1 |       87 | 50.0% |  14.3% | 1.6× | 6.8% |   0.3218 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   35 |   13.1 | 2.9% | 0.428 | 0.0 |       33 | 100.0% |  20.0% | 6.6× | 0.0% |   0.1515 |
|       OK |   22 |   36.9 | 0.0% | 0.335 | 0.0 |       21 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   34 |  118.1 | 0.0% | 0.320 | 0.0 |       33 |    - |   0.0% |    - | 0.0% |   0.0909 |
|      ALL |   91 |   58.1 | 1.1% | 0.365 | 0.0 |       87 | 100.0% |  12.5% | 10.9× | 0.0% |   0.0920 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   35 |   13.1 | 2.9% | 0.246 | 0.0 |       33 | 0.0% |   0.0% |    - | 3.3% |   0.0909 |
|       OK |   22 |   36.9 | 9.1% | 0.323 | 0.1 |       21 | 0.0% |      - |    - | 9.5% |   0.0000 |
| DEGRADED |   34 |  118.1 | 5.9% | 0.262 | 0.1 |       33 | 0.0% |   0.0% |    - | 3.1% |   0.0303 |
|      ALL |   91 |   58.1 | 5.5% | 0.271 | 0.1 |       87 | 0.0% |   0.0% |    - | 4.8% |   0.0460 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   14.7 | 0.0% | 0.375 | 0.0 |        8 |    - |   0.0% |    - | 0.0% |   0.2500 |
|       OK |    8 |   39.2 | 0.0% | 0.395 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |   87.3 | 15.4% | 0.445 | 0.1 |       12 | 0.0% |   0.0% |    - | 28.6% |   0.4167 |
|      ALL |   31 |   51.5 | 6.5% | 0.409 | 0.1 |       27 | 0.0% |   0.0% |    - | 10.0% |   0.2593 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   14.7 | 0.0% | 0.347 | 0.0 |        8 |    - |   0.0% |    - | 0.0% |   0.1250 |
|       OK |    8 |   39.2 | 0.0% | 0.294 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |   87.3 | 0.0% | 0.342 | 0.0 |       12 |    - |   0.0% |    - | 0.0% |   0.1667 |
|      ALL |   31 |   51.5 | 0.0% | 0.332 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.1111 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   14.7 | 0.0% | 0.227 | 0.0 |        8 |    - |   0.0% |    - | 0.0% |   0.1250 |
|       OK |    8 |   39.2 | 12.5% | 0.338 | 0.1 |        7 | 0.0% |      - |    - | 14.3% |   0.0000 |
| DEGRADED |   13 |   87.3 | 7.7% | 0.342 | 0.1 |       12 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   51.5 | 6.5% | 0.304 | 0.1 |       27 | 0.0% |   0.0% |    - | 3.9% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available