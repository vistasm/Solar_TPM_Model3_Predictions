# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-08-13 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (81.8%) is 81.8% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (11.3%) is 2.5× the overall rate (4.5%) — score distribution shift detected
🟢 **X+**: FRESH precision (16.7%) is 16.7% HIGHER than DEGRADED (0.0%) — fresher data is helping

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   62 |   12.4 | 17.7% | 0.510 | 0.2 |       62 | 81.8% |  31.0% | 1.8× | 6.1% |   0.4677 |
|       OK |   32 |   36.7 | 6.2% | 0.402 | 0.1 |       32 | 50.0% |  25.0% | 4.0× | 3.6% |   0.1250 |
| DEGRADED |   60 |  118.6 | 8.3% | 0.407 | 0.1 |       58 | 0.0% |   0.0% |    - | 11.4% |   0.2414 |
|      ALL |  154 |   58.8 | 11.7% | 0.448 | 0.1 |      152 | 55.6% |  21.3% | 1.8× | 7.6% |   0.3092 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   62 |   12.4 | 11.3% | 0.498 | 0.1 |       62 | 57.1% |  36.4% | 3.2× | 5.9% |   0.1774 |
|       OK |   32 |   36.7 | 0.0% | 0.329 | 0.0 |       32 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   60 |  118.6 | 0.0% | 0.336 | 0.0 |       58 |    - |   0.0% |    - | 0.0% |   0.0517 |
|      ALL |  154 |   58.8 | 4.5% | 0.400 | 0.1 |      152 | 57.1% |  28.6% | 6.2× | 2.2% |   0.0921 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   62 |   12.4 | 9.7% | 0.357 | 0.1 |       62 | 16.7% |  20.0% | 2.1× | 8.8% |   0.0806 |
|       OK |   32 |   36.7 | 6.2% | 0.315 | 0.1 |       32 | 0.0% |      - |    - | 6.2% |   0.0000 |
| DEGRADED |   60 |  118.6 | 5.0% | 0.290 | 0.1 |       58 | 0.0% |   0.0% |    - | 5.3% |   0.0172 |
|      ALL |  154 |   58.8 | 7.1% | 0.322 | 0.1 |      152 | 9.1% |  16.7% | 2.3× | 6.9% |   0.0395 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    7 |   14.3 | 14.3% | 0.549 | 0.1 |        7 | 100.0% |  50.0% | 3.5× | 0.0% |   0.2857 |
|       OK |    6 |   36.4 | 16.7% | 0.403 | 0.2 |        6 | 0.0% |      - |    - | 16.7% |   0.0000 |
| DEGRADED |   16 |  124.6 | 0.0% | 0.363 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.2143 |
|      ALL |   29 |   79.7 | 6.9% | 0.416 | 0.1 |       27 | 50.0% |  20.0% | 2.7× | 4.5% |   0.1852 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    7 |   14.3 | 14.3% | 0.565 | 0.1 |        7 | 0.0% |      - |    - | 14.3% |   0.0000 |
|       OK |    6 |   36.4 | 0.0% | 0.306 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   16 |  124.6 | 0.0% | 0.294 | 0.0 |       14 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   29 |   79.7 | 3.5% | 0.362 | 0.0 |       27 | 0.0% |      - |    - | 3.7% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    7 |   14.3 | 0.0% | 0.398 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    6 |   36.4 | 0.0% | 0.306 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   16 |  124.6 | 0.0% | 0.236 | 0.0 |       14 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   29 |   79.7 | 0.0% | 0.290 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available