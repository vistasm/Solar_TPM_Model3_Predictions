# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-05-07 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (100.0%) is 100.0% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (4.2%) is 2.4× the overall rate (1.7%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   24 |   12.4 | 12.5% | 0.486 | 0.1 |       23 | 100.0% |  21.4% | 1.6× | 0.0% |   0.6087 |
|       OK |   13 |   35.4 | 7.7% | 0.429 | 0.1 |       12 | 100.0% |  33.3% | 4.0× | 0.0% |   0.2500 |
| DEGRADED |   21 |  137.1 | 9.5% | 0.366 | 0.1 |       19 | 0.0% |   0.0% |    - | 12.5% |   0.1579 |
|      ALL |   58 |   62.7 | 10.3% | 0.430 | 0.1 |       54 | 66.7% |  20.0% | 1.8× | 5.9% |   0.3704 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   24 |   12.4 | 4.2% | 0.472 | 0.0 |       23 | 100.0% |  25.0% | 5.8× | 0.0% |   0.1739 |
|       OK |   13 |   35.4 | 0.0% | 0.372 | 0.0 |       12 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   21 |  137.1 | 0.0% | 0.307 | 0.0 |       19 |    - |   0.0% |    - | 0.0% |   0.0526 |
|      ALL |   58 |   62.7 | 1.7% | 0.390 | 0.0 |       54 | 100.0% |  20.0% | 10.8× | 0.0% |   0.0926 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   24 |   12.4 | 4.2% | 0.262 | 0.0 |       23 | 0.0% |   0.0% |    - | 4.8% |   0.0870 |
|       OK |   13 |   35.4 | 7.7% | 0.335 | 0.1 |       12 | 0.0% |      - |    - | 8.3% |   0.0000 |
| DEGRADED |   21 |  137.1 | 4.8% | 0.212 | 0.1 |       19 | 0.0% |   0.0% |    - | 5.6% |   0.0526 |
|      ALL |   58 |   62.7 | 5.2% | 0.260 | 0.1 |       54 | 0.0% |   0.0% |    - | 5.9% |   0.0556 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   11.2 | 33.3% | 0.612 | 0.3 |        8 | 100.0% |  50.0% | 1.3× | 0.0% |   0.7500 |
|       OK |    4 |   35.6 | 25.0% | 0.464 | 0.2 |        3 | 100.0% | 100.0% | 3.0× | 0.0% |   0.3333 |
| DEGRADED |   17 |  149.2 | 0.0% | 0.353 | 0.0 |       15 |    - |   0.0% |    - | 0.0% |   0.1333 |
|      ALL |   30 |   92.6 | 13.3% | 0.445 | 0.1 |       26 | 100.0% |  44.4% | 2.9× | 0.0% |   0.3462 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   11.2 | 11.1% | 0.604 | 0.1 |        8 | 100.0% |  50.0% | 4.0× | 0.0% |   0.2500 |
|       OK |    4 |   35.6 | 0.0% | 0.340 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   17 |  149.2 | 0.0% | 0.300 | 0.0 |       15 |    - |   0.0% |    - | 0.0% |   0.0667 |
|      ALL |   30 |   92.6 | 3.3% | 0.397 | 0.0 |       26 | 100.0% |  33.3% | 8.7× | 0.0% |   0.1154 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   11.2 | 0.0% | 0.291 | 0.0 |        8 |    - |   0.0% |    - | 0.0% |   0.1250 |
|       OK |    4 |   35.6 | 25.0% | 0.363 | 0.2 |        3 | 0.0% |      - |    - | 33.3% |   0.0000 |
| DEGRADED |   17 |  149.2 | 0.0% | 0.152 | 0.0 |       15 |    - |   0.0% |    - | 0.0% |   0.0667 |
|      ALL |   30 |   92.6 | 3.3% | 0.222 | 0.0 |       26 | 0.0% |   0.0% |    - | 4.2% |   0.0769 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available