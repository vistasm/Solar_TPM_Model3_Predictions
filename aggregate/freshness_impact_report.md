# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-06-05 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (100.0%) is 100.0% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (3.0%) is 2.6× the overall rate (1.1%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   33 |   13.0 | 9.1% | 0.447 | 0.1 |       31 | 100.0% |  20.0% | 2.1× | 0.0% |   0.4839 |
|       OK |   21 |   36.8 | 4.8% | 0.406 | 0.1 |       20 | 100.0% |  33.3% | 6.7× | 0.0% |   0.1500 |
| DEGRADED |   33 |  119.7 | 12.1% | 0.385 | 0.1 |       32 | 0.0% |   0.0% |    - | 16.7% |   0.2500 |
|      ALL |   87 |   59.2 | 9.2% | 0.413 | 0.1 |       83 | 50.0% |  15.4% | 1.6× | 7.0% |   0.3133 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   33 |   13.0 | 3.0% | 0.424 | 0.0 |       31 | 100.0% |  25.0% | 7.8× | 0.0% |   0.1290 |
|       OK |   21 |   36.8 | 0.0% | 0.334 | 0.0 |       20 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   33 |  119.7 | 0.0% | 0.310 | 0.0 |       32 |    - |   0.0% |    - | 0.0% |   0.0625 |
|      ALL |   87 |   59.2 | 1.1% | 0.359 | 0.0 |       83 | 100.0% |  16.7% | 13.8× | 0.0% |   0.0723 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   33 |   13.0 | 3.0% | 0.243 | 0.0 |       31 | 0.0% |   0.0% |    - | 3.5% |   0.0645 |
|       OK |   21 |   36.8 | 9.5% | 0.326 | 0.1 |       20 | 0.0% |      - |    - | 5.0% |   0.0000 |
| DEGRADED |   33 |  119.7 | 3.0% | 0.240 | 0.0 |       32 | 0.0% |   0.0% |    - | 3.2% |   0.0312 |
|      ALL |   87 |   59.2 | 4.6% | 0.262 | 0.1 |       83 | 0.0% |   0.0% |    - | 3.8% |   0.0361 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   14.7 | 0.0% | 0.343 | 0.0 |        7 |    - |   0.0% |    - | 0.0% |   0.1429 |
|       OK |    8 |   39.0 | 0.0% | 0.368 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   14 |   85.6 | 14.3% | 0.394 | 0.1 |       13 | 0.0% |   0.0% |    - | 25.0% |   0.3846 |
|      ALL |   31 |   53.0 | 6.5% | 0.372 | 0.1 |       27 | 0.0% |   0.0% |    - | 9.5% |   0.2222 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   14.7 | 0.0% | 0.296 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    8 |   39.0 | 0.0% | 0.271 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   14 |   85.6 | 0.0% | 0.298 | 0.0 |       13 |    - |   0.0% |    - | 0.0% |   0.0769 |
|      ALL |   31 |   53.0 | 0.0% | 0.291 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0370 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   14.7 | 0.0% | 0.191 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    8 |   39.0 | 12.5% | 0.312 | 0.1 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   14 |   85.6 | 0.0% | 0.255 | 0.0 |       13 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   53.0 | 3.2% | 0.251 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available