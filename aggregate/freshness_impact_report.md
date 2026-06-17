# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-06-17 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (75.0%) is 75.0% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (2.6%) is 2.5× the overall rate (1.0%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   39 |   13.1 | 10.3% | 0.451 | 0.1 |       38 | 75.0% |  17.6% | 1.7× | 4.8% |   0.4474 |
|       OK |   24 |   37.4 | 4.2% | 0.389 | 0.0 |       23 | 100.0% |  33.3% | 7.7× | 0.0% |   0.1304 |
| DEGRADED |   36 |  115.7 | 11.1% | 0.393 | 0.1 |       34 | 0.0% |   0.0% |    - | 16.0% |   0.2647 |
|      ALL |   99 |   56.3 | 9.1% | 0.415 | 0.1 |       95 | 44.4% |  13.8% | 1.5× | 7.6% |   0.3053 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   39 |   13.1 | 2.6% | 0.438 | 0.0 |       38 | 100.0% |  20.0% | 7.6× | 0.0% |   0.1316 |
|       OK |   24 |   37.4 | 0.0% | 0.321 | 0.0 |       23 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   36 |  115.7 | 0.0% | 0.323 | 0.0 |       34 |    - |   0.0% |    - | 0.0% |   0.0882 |
|      ALL |   99 |   56.3 | 1.0% | 0.368 | 0.0 |       95 | 100.0% |  12.5% | 11.9× | 0.0% |   0.0842 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   39 |   13.1 | 5.1% | 0.276 | 0.1 |       38 | 0.0% |   0.0% |    - | 5.7% |   0.0789 |
|       OK |   24 |   37.4 | 8.3% | 0.307 | 0.1 |       23 | 0.0% |      - |    - | 8.7% |   0.0000 |
| DEGRADED |   36 |  115.7 | 5.6% | 0.264 | 0.1 |       34 | 0.0% |   0.0% |    - | 6.1% |   0.0294 |
|      ALL |   99 |   56.3 | 6.1% | 0.279 | 0.1 |       95 | 0.0% |   0.0% |    - | 6.6% |   0.0421 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   15.0 | 9.1% | 0.399 | 0.1 |       10 | 0.0% |   0.0% |    - | 12.5% |   0.2000 |
|       OK |    8 |   40.7 | 0.0% | 0.355 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   12 |   89.4 | 16.7% | 0.436 | 0.2 |       10 | 0.0% |   0.0% |    - | 33.3% |   0.4000 |
|      ALL |   31 |   50.4 | 9.7% | 0.402 | 0.1 |       27 | 0.0% |   0.0% |    - | 14.3% |   0.2222 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   15.0 | 0.0% | 0.401 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.1000 |
|       OK |    8 |   40.7 | 0.0% | 0.259 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   12 |   89.4 | 0.0% | 0.345 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.1000 |
|      ALL |   31 |   50.4 | 0.0% | 0.343 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   15.0 | 9.1% | 0.319 | 0.1 |       10 | 0.0% |   0.0% |    - | 11.1% |   0.1000 |
|       OK |    8 |   40.7 | 12.5% | 0.347 | 0.1 |        7 | 0.0% |      - |    - | 14.3% |   0.0000 |
| DEGRADED |   12 |   89.4 | 8.3% | 0.356 | 0.1 |       10 | 0.0% |      - |    - | 10.0% |   0.0000 |
|      ALL |   31 |   50.4 | 9.7% | 0.341 | 0.1 |       27 | 0.0% |   0.0% |    - | 11.5% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available