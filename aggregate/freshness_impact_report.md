# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-08-10 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (81.8%) is 81.8% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (11.3%) is 2.5× the overall rate (4.6%) — score distribution shift detected
🟢 **X+**: FRESH precision (16.7%) is 16.7% HIGHER than DEGRADED (0.0%) — fresher data is helping

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   62 |   12.4 | 17.7% | 0.510 | 0.2 |       62 | 81.8% |  31.0% | 1.8× | 6.1% |   0.4677 |
|       OK |   32 |   36.7 | 6.2% | 0.402 | 0.1 |       32 | 50.0% |  25.0% | 4.0× | 3.6% |   0.1250 |
| DEGRADED |   59 |  119.5 | 8.5% | 0.405 | 0.1 |       55 | 0.0% |   0.0% |    - | 12.2% |   0.2545 |
|      ALL |  153 |   58.8 | 11.8% | 0.447 | 0.1 |      149 | 55.6% |  21.3% | 1.8× | 7.8% |   0.3154 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   62 |   12.4 | 11.3% | 0.498 | 0.1 |       62 | 57.1% |  36.4% | 3.2× | 5.9% |   0.1774 |
|       OK |   32 |   36.7 | 0.0% | 0.329 | 0.0 |       32 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   59 |  119.5 | 0.0% | 0.333 | 0.0 |       55 |    - |   0.0% |    - | 0.0% |   0.0545 |
|      ALL |  153 |   58.8 | 4.6% | 0.399 | 0.1 |      149 | 57.1% |  28.6% | 6.1× | 2.2% |   0.0940 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   62 |   12.4 | 9.7% | 0.357 | 0.1 |       62 | 16.7% |  20.0% | 2.1× | 8.8% |   0.0806 |
|       OK |   32 |   36.7 | 6.2% | 0.315 | 0.1 |       32 | 0.0% |      - |    - | 6.2% |   0.0000 |
| DEGRADED |   59 |  119.5 | 5.1% | 0.291 | 0.1 |       55 | 0.0% |   0.0% |    - | 5.6% |   0.0182 |
|      ALL |  153 |   58.8 | 7.2% | 0.323 | 0.1 |      149 | 9.1% |  16.7% | 2.3× | 7.0% |   0.0403 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   14.0 | 10.0% | 0.550 | 0.1 |       10 | 100.0% |  33.3% | 3.3× | 0.0% |   0.3000 |
|       OK |    6 |   36.4 | 16.7% | 0.403 | 0.2 |        6 | 0.0% |      - |    - | 16.7% |   0.0000 |
| DEGRADED |   15 |  128.6 | 0.0% | 0.352 | 0.0 |       11 |    - |   0.0% |    - | 0.0% |   0.2727 |
|      ALL |   31 |   73.8 | 6.5% | 0.426 | 0.1 |       27 | 50.0% |  16.7% | 2.2× | 4.8% |   0.2222 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   14.0 | 10.0% | 0.549 | 0.1 |       10 | 0.0% |      - |    - | 10.0% |   0.0000 |
|       OK |    6 |   36.4 | 0.0% | 0.306 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   15 |  128.6 | 0.0% | 0.280 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   73.8 | 3.2% | 0.372 | 0.0 |       27 | 0.0% |      - |    - | 3.7% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   14.0 | 0.0% | 0.376 | 0.0 |       10 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    6 |   36.4 | 0.0% | 0.306 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   15 |  128.6 | 0.0% | 0.237 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   73.8 | 0.0% | 0.295 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available