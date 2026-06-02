# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-06-02 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (100.0%) is 100.0% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (3.2%) is 2.7× the overall rate (1.2%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   31 |   13.1 | 9.7% | 0.448 | 0.1 |       30 | 100.0% |  20.0% | 2.0× | 0.0% |   0.5000 |
|       OK |   20 |   36.5 | 5.0% | 0.403 | 0.1 |       19 | 100.0% |  33.3% | 6.3× | 0.0% |   0.1579 |
| DEGRADED |   33 |  119.7 | 12.1% | 0.385 | 0.1 |       31 | 0.0% |   0.0% |    - | 16.7% |   0.2258 |
|      ALL |   84 |   60.6 | 9.5% | 0.413 | 0.1 |       80 | 50.0% |  16.0% | 1.6× | 7.3% |   0.3125 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   31 |   13.1 | 3.2% | 0.424 | 0.0 |       30 | 100.0% |  25.0% | 7.5× | 0.0% |   0.1333 |
|       OK |   20 |   36.5 | 0.0% | 0.332 | 0.0 |       19 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   33 |  119.7 | 0.0% | 0.310 | 0.0 |       31 |    - |   0.0% |    - | 0.0% |   0.0645 |
|      ALL |   84 |   60.6 | 1.2% | 0.357 | 0.0 |       80 | 100.0% |  16.7% | 13.3× | 0.0% |   0.0750 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   31 |   13.1 | 3.2% | 0.240 | 0.0 |       30 | 0.0% |   0.0% |    - | 3.6% |   0.0667 |
|       OK |   20 |   36.5 | 5.0% | 0.296 | 0.1 |       19 | 0.0% |      - |    - | 5.3% |   0.0000 |
| DEGRADED |   33 |  119.7 | 3.0% | 0.240 | 0.0 |       31 | 0.0% |   0.0% |    - | 3.3% |   0.0323 |
|      ALL |   84 |   60.6 | 3.6% | 0.254 | 0.0 |       80 | 0.0% |   0.0% |    - | 3.9% |   0.0375 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   13.9 | 0.0% | 0.348 | 0.0 |        8 |    - |   0.0% |    - | 0.0% |   0.2500 |
|       OK |    8 |   37.3 | 0.0% | 0.350 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   14 |   85.6 | 14.3% | 0.394 | 0.1 |       12 | 0.0% |   0.0% |    - | 25.0% |   0.3333 |
|      ALL |   31 |   52.3 | 6.5% | 0.369 | 0.1 |       27 | 0.0% |   0.0% |    - | 9.5% |   0.2222 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   13.9 | 0.0% | 0.281 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    8 |   37.3 | 0.0% | 0.255 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   14 |   85.6 | 0.0% | 0.298 | 0.0 |       12 |    - |   0.0% |    - | 0.0% |   0.0833 |
|      ALL |   31 |   52.3 | 0.0% | 0.282 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0370 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   13.9 | 0.0% | 0.181 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    8 |   37.3 | 0.0% | 0.239 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   14 |   85.6 | 0.0% | 0.255 | 0.0 |       12 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   52.3 | 0.0% | 0.229 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available