# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-08-03 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (81.8%) is 81.8% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (11.3%) is 2.4× the overall rate (4.8%) — score distribution shift detected
🟢 **X+**: FRESH precision (16.7%) is 16.7% HIGHER than DEGRADED (0.0%) — fresher data is helping

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   62 |   12.4 | 17.7% | 0.510 | 0.2 |       61 | 81.8% |  31.0% | 1.7× | 6.2% |   0.4754 |
|       OK |   32 |   36.7 | 6.2% | 0.402 | 0.1 |       31 | 100.0% |  25.0% | 7.8× | 0.0% |   0.1290 |
| DEGRADED |   52 |  111.3 | 9.6% | 0.419 | 0.1 |       50 | 0.0% |   0.0% |    - | 13.9% |   0.2800 |
|      ALL |  146 |   53.0 | 12.3% | 0.454 | 0.1 |      142 | 58.8% |  21.3% | 1.8× | 7.4% |   0.3310 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   62 |   12.4 | 11.3% | 0.498 | 0.1 |       61 | 57.1% |  36.4% | 3.2× | 6.0% |   0.1803 |
|       OK |   32 |   36.7 | 0.0% | 0.329 | 0.0 |       31 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   52 |  111.3 | 0.0% | 0.347 | 0.0 |       50 |    - |   0.0% |    - | 0.0% |   0.0600 |
|      ALL |  146 |   53.0 | 4.8% | 0.407 | 0.1 |      142 | 57.1% |  28.6% | 5.8× | 2.3% |   0.0986 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   62 |   12.4 | 9.7% | 0.357 | 0.1 |       61 | 16.7% |  20.0% | 2.0× | 8.9% |   0.0820 |
|       OK |   32 |   36.7 | 6.2% | 0.315 | 0.1 |       31 | 0.0% |      - |    - | 6.5% |   0.0000 |
| DEGRADED |   52 |  111.3 | 5.8% | 0.309 | 0.1 |       50 | 0.0% |   0.0% |    - | 6.1% |   0.0200 |
|      ALL |  146 |   53.0 | 7.5% | 0.331 | 0.1 |      142 | 9.1% |  16.7% | 2.1× | 7.3% |   0.0423 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   16 |   12.9 | 25.0% | 0.599 | 0.3 |       15 | 75.0% |  50.0% | 1.9× | 11.1% |   0.4000 |
|       OK |    7 |   34.7 | 14.3% | 0.423 | 0.1 |        6 |    - |   0.0% |    - | 0.0% |   0.1667 |
| DEGRADED |    8 |   83.3 | 0.0% | 0.399 | 0.0 |        6 |    - |   0.0% |    - | 0.0% |   0.5000 |
|      ALL |   31 |   36.0 | 16.1% | 0.507 | 0.2 |       27 | 75.0% |  30.0% | 2.0× | 5.9% |   0.3704 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   16 |   12.9 | 25.0% | 0.591 | 0.2 |       15 | 50.0% | 100.0% | 3.8× | 15.4% |   0.1333 |
|       OK |    7 |   34.7 | 0.0% | 0.352 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    8 |   83.3 | 0.0% | 0.321 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   36.0 | 12.9% | 0.467 | 0.1 |       27 | 50.0% | 100.0% | 6.8× | 8.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   16 |   12.9 | 18.8% | 0.454 | 0.2 |       15 | 33.3% | 100.0% | 5.0× | 14.3% |   0.0667 |
|       OK |    7 |   34.7 | 0.0% | 0.352 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    8 |   83.3 | 0.0% | 0.304 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   36.0 | 9.7% | 0.393 | 0.1 |       27 | 33.3% | 100.0% | 9.0× | 7.7% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available