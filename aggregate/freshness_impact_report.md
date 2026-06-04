# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-06-04 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (100.0%) is 100.0% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (3.0%) is 2.6× the overall rate (1.2%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   33 |   13.0 | 9.1% | 0.447 | 0.1 |       31 | 100.0% |  20.0% | 2.1× | 0.0% |   0.4839 |
|       OK |   20 |   36.5 | 5.0% | 0.403 | 0.1 |       20 | 100.0% |  33.3% | 6.7× | 0.0% |   0.1500 |
| DEGRADED |   33 |  119.7 | 12.1% | 0.385 | 0.1 |       31 | 0.0% |   0.0% |    - | 16.7% |   0.2258 |
|      ALL |   86 |   59.4 | 9.3% | 0.413 | 0.1 |       82 | 50.0% |  16.0% | 1.6× | 7.0% |   0.3049 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   33 |   13.0 | 3.0% | 0.424 | 0.0 |       31 | 100.0% |  25.0% | 7.8× | 0.0% |   0.1290 |
|       OK |   20 |   36.5 | 0.0% | 0.332 | 0.0 |       20 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   33 |  119.7 | 0.0% | 0.310 | 0.0 |       31 |    - |   0.0% |    - | 0.0% |   0.0645 |
|      ALL |   86 |   59.4 | 1.2% | 0.359 | 0.0 |       82 | 100.0% |  16.7% | 13.7× | 0.0% |   0.0732 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   33 |   13.0 | 3.0% | 0.243 | 0.0 |       31 | 0.0% |   0.0% |    - | 3.5% |   0.0645 |
|       OK |   20 |   36.5 | 5.0% | 0.296 | 0.1 |       20 | 0.0% |      - |    - | 5.0% |   0.0000 |
| DEGRADED |   33 |  119.7 | 3.0% | 0.240 | 0.0 |       31 | 0.0% |   0.0% |    - | 3.3% |   0.0323 |
|      ALL |   86 |   59.4 | 3.5% | 0.254 | 0.0 |       82 | 0.0% |   0.0% |    - | 3.8% |   0.0366 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   14.7 | 0.0% | 0.343 | 0.0 |        7 |    - |   0.0% |    - | 0.0% |   0.1429 |
|       OK |    8 |   37.3 | 0.0% | 0.350 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   14 |   85.6 | 14.3% | 0.394 | 0.1 |       12 | 0.0% |   0.0% |    - | 25.0% |   0.3333 |
|      ALL |   31 |   52.5 | 6.5% | 0.368 | 0.1 |       27 | 0.0% |   0.0% |    - | 9.1% |   0.1852 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   14.7 | 0.0% | 0.296 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    8 |   37.3 | 0.0% | 0.255 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   14 |   85.6 | 0.0% | 0.298 | 0.0 |       12 |    - |   0.0% |    - | 0.0% |   0.0833 |
|      ALL |   31 |   52.5 | 0.0% | 0.287 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0370 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   14.7 | 0.0% | 0.191 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    8 |   37.3 | 0.0% | 0.239 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   14 |   85.6 | 0.0% | 0.255 | 0.0 |       12 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   52.5 | 0.0% | 0.232 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available