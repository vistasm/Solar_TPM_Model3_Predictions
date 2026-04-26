# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-04-26 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟡 **M5+**: FRESH alert rate (5.3%) is 2.5× the overall rate (2.1%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   19 |   12.5 | 15.8% | 0.460 | 0.2 |       16 |    - |   0.0% |    - | 0.0% |   0.5000 |
|       OK |   11 |   35.7 | 9.1% | 0.438 | 0.1 |       11 | 100.0% |  33.3% | 3.7× | 0.0% |   0.2727 |
| DEGRADED |   17 |  153.0 | 11.8% | 0.373 | 0.1 |       16 | 0.0% |   0.0% |    - | 14.3% |   0.1250 |
|      ALL |   47 |   68.7 | 12.8% | 0.423 | 0.1 |       43 | 33.3% |   7.7% | 1.1× | 6.7% |   0.3023 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   19 |   12.5 | 5.3% | 0.451 | 0.1 |       16 |    - |   0.0% |    - | 0.0% |   0.1250 |
|       OK |   11 |   35.7 | 0.0% | 0.387 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   17 |  153.0 | 0.0% | 0.325 | 0.0 |       16 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   47 |   68.7 | 2.1% | 0.390 | 0.0 |       43 |    - |   0.0% |    - | 0.0% |   0.0465 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   19 |   12.5 | 5.3% | 0.272 | 0.1 |       16 | 0.0% |   0.0% |    - | 6.7% |   0.0625 |
|       OK |   11 |   35.7 | 9.1% | 0.357 | 0.1 |       11 | 0.0% |      - |    - | 9.1% |   0.0000 |
| DEGRADED |   17 |  153.0 | 5.9% | 0.245 | 0.1 |       16 | 0.0% |      - |    - | 6.2% |   0.0000 |
|      ALL |   47 |   68.7 | 6.4% | 0.282 | 0.1 |       43 | 0.0% |   0.0% |    - | 7.1% |   0.0233 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   11.0 | 25.0% | 0.477 | 0.2 |        9 |    - |   0.0% |    - | 0.0% |   0.5556 |
|       OK |    5 |   35.7 | 20.0% | 0.460 | 0.2 |        5 | 100.0% | 100.0% | 5.0× | 0.0% |   0.2000 |
| DEGRADED |   13 |  173.6 | 0.0% | 0.357 | 0.0 |       12 |    - |   0.0% |    - | 0.0% |   0.0833 |
|      ALL |   30 |   85.6 | 13.3% | 0.422 | 0.1 |       26 | 100.0% |  14.3% | 3.7× | 0.0% |   0.2692 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   11.0 | 8.3% | 0.502 | 0.1 |        9 |    - |   0.0% |    - | 0.0% |   0.2222 |
|       OK |    5 |   35.7 | 0.0% | 0.434 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |  173.6 | 0.0% | 0.322 | 0.0 |       12 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   30 |   85.6 | 3.3% | 0.412 | 0.0 |       26 |    - |   0.0% |    - | 0.0% |   0.0769 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   11.0 | 8.3% | 0.330 | 0.1 |        9 | 0.0% |   0.0% |    - | 12.5% |   0.1111 |
|       OK |    5 |   35.7 | 20.0% | 0.344 | 0.2 |        5 | 0.0% |      - |    - | 20.0% |   0.0000 |
| DEGRADED |   13 |  173.6 | 0.0% | 0.177 | 0.0 |       12 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   30 |   85.6 | 6.7% | 0.266 | 0.1 |       26 | 0.0% |   0.0% |    - | 8.0% |   0.0385 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available