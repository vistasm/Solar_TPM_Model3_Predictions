# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-08-08 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (81.8%) is 81.8% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (11.3%) is 2.4× the overall rate (4.6%) — score distribution shift detected
🟢 **X+**: FRESH precision (16.7%) is 16.7% HIGHER than DEGRADED (0.0%) — fresher data is helping

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   62 |   12.4 | 17.7% | 0.510 | 0.2 |       62 | 81.8% |  31.0% | 1.8× | 6.1% |   0.4677 |
|       OK |   32 |   36.7 | 6.2% | 0.402 | 0.1 |       32 | 50.0% |  25.0% | 4.0× | 3.6% |   0.1250 |
| DEGRADED |   57 |  115.3 | 8.8% | 0.412 | 0.1 |       53 | 0.0% |   0.0% |    - | 12.8% |   0.2642 |
|      ALL |  151 |   56.4 | 11.9% | 0.450 | 0.1 |      147 | 55.6% |  21.3% | 1.7× | 8.0% |   0.3197 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   62 |   12.4 | 11.3% | 0.498 | 0.1 |       62 | 57.1% |  36.4% | 3.2× | 5.9% |   0.1774 |
|       OK |   32 |   36.7 | 0.0% | 0.329 | 0.0 |       32 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   57 |  115.3 | 0.0% | 0.342 | 0.0 |       53 |    - |   0.0% |    - | 0.0% |   0.0566 |
|      ALL |  151 |   56.4 | 4.6% | 0.403 | 0.1 |      147 | 57.1% |  28.6% | 6.0× | 2.3% |   0.0952 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   62 |   12.4 | 9.7% | 0.357 | 0.1 |       62 | 16.7% |  20.0% | 2.1× | 8.8% |   0.0806 |
|       OK |   32 |   36.7 | 6.2% | 0.315 | 0.1 |       32 | 0.0% |      - |    - | 6.2% |   0.0000 |
| DEGRADED |   57 |  115.3 | 5.3% | 0.299 | 0.1 |       53 | 0.0% |   0.0% |    - | 5.8% |   0.0189 |
|      ALL |  151 |   56.4 | 7.3% | 0.326 | 0.1 |      147 | 9.1% |  16.7% | 2.2× | 7.1% |   0.0408 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   14.5 | 8.3% | 0.517 | 0.1 |       12 | 100.0% |  33.3% | 4.0× | 0.0% |   0.2500 |
|       OK |    6 |   36.4 | 16.7% | 0.403 | 0.2 |        6 | 0.0% |      - |    - | 16.7% |   0.0000 |
| DEGRADED |   13 |  111.4 | 0.0% | 0.375 | 0.0 |        9 |    - |   0.0% |    - | 0.0% |   0.3333 |
|      ALL |   31 |   59.4 | 6.5% | 0.436 | 0.1 |       27 | 50.0% |  16.7% | 2.2× | 4.8% |   0.2222 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   14.5 | 8.3% | 0.512 | 0.1 |       12 | 0.0% |      - |    - | 8.3% |   0.0000 |
|       OK |    6 |   36.4 | 0.0% | 0.306 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |  111.4 | 0.0% | 0.309 | 0.0 |        9 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   59.4 | 3.2% | 0.387 | 0.0 |       27 | 0.0% |      - |    - | 3.7% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   14.5 | 0.0% | 0.346 | 0.0 |       12 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    6 |   36.4 | 0.0% | 0.306 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |  111.4 | 0.0% | 0.261 | 0.0 |        9 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   59.4 | 0.0% | 0.302 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available