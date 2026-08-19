# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-08-19 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (81.8%) is 81.8% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (10.9%) is 2.5× the overall rate (4.4%) — score distribution shift detected
🟢 **X+**: FRESH precision (16.7%) is 16.7% HIGHER than DEGRADED (0.0%) — fresher data is helping

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   64 |   12.6 | 18.8% | 0.512 | 0.2 |       63 | 81.8% |  31.0% | 1.8× | 5.9% |   0.4603 |
|       OK |   34 |   37.0 | 8.8% | 0.411 | 0.1 |       32 | 50.0% |  25.0% | 4.0× | 3.6% |   0.1250 |
| DEGRADED |   61 |  118.1 | 8.2% | 0.406 | 0.1 |       61 | 0.0% |   0.0% |    - | 10.6% |   0.2295 |
|      ALL |  159 |   58.3 | 12.6% | 0.450 | 0.1 |      156 | 55.6% |  21.3% | 1.8× | 7.3% |   0.3013 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   64 |   12.6 | 10.9% | 0.503 | 0.1 |       63 | 57.1% |  36.4% | 3.3× | 5.8% |   0.1746 |
|       OK |   34 |   37.0 | 0.0% | 0.344 | 0.0 |       32 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   61 |  118.1 | 0.0% | 0.337 | 0.0 |       61 |    - |   0.0% |    - | 0.0% |   0.0492 |
|      ALL |  159 |   58.3 | 4.4% | 0.405 | 0.0 |      156 | 57.1% |  28.6% | 6.4× | 2.1% |   0.0897 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   64 |   12.6 | 9.4% | 0.357 | 0.1 |       63 | 16.7% |  20.0% | 2.1× | 8.6% |   0.0794 |
|       OK |   34 |   37.0 | 5.9% | 0.315 | 0.1 |       32 | 0.0% |      - |    - | 6.2% |   0.0000 |
| DEGRADED |   61 |  118.1 | 4.9% | 0.291 | 0.1 |       61 | 0.0% |   0.0% |    - | 5.0% |   0.0164 |
|      ALL |  159 |   58.3 | 6.9% | 0.322 | 0.1 |      156 | 9.1% |  16.7% | 2.4× | 6.7% |   0.0385 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   14.8 | 25.0% | 0.595 | 0.2 |        7 | 100.0% |  50.0% | 3.5× | 0.0% |   0.2857 |
|       OK |    6 |   35.9 | 33.3% | 0.516 | 0.3 |        4 | 0.0% |      - |    - | 25.0% |   0.0000 |
| DEGRADED |   14 |  129.6 | 0.0% | 0.403 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.2143 |
|      ALL |   28 |   76.7 | 14.3% | 0.482 | 0.1 |       25 | 50.0% |  20.0% | 2.5× | 5.0% |   0.2000 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   14.8 | 12.5% | 0.639 | 0.1 |        7 | 0.0% |      - |    - | 14.3% |   0.0000 |
|       OK |    6 |   35.9 | 0.0% | 0.452 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   14 |  129.6 | 0.0% | 0.343 | 0.0 |       14 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   28 |   76.7 | 3.6% | 0.451 | 0.0 |       25 | 0.0% |      - |    - | 4.0% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   14.8 | 0.0% | 0.421 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    6 |   35.9 | 0.0% | 0.359 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   14 |  129.6 | 0.0% | 0.286 | 0.0 |       14 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   28 |   76.7 | 0.0% | 0.340 | 0.0 |       25 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available