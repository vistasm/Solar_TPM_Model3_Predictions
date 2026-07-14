# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-07-14 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (80.0%) is 80.0% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (10.9%) is 2.3× the overall rate (4.8%) — score distribution shift detected
🟢 **X+**: FRESH precision (16.7%) is 16.7% HIGHER than DEGRADED (0.0%) — fresher data is helping

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   55 |   12.2 | 18.2% | 0.505 | 0.2 |       52 | 80.0% |  30.8% | 1.6× | 7.7% |   0.5000 |
|       OK |   27 |   37.1 | 3.7% | 0.398 | 0.0 |       26 | 100.0% |  25.0% | 6.5× | 0.0% |   0.1538 |
| DEGRADED |   44 |  116.4 | 11.4% | 0.423 | 0.1 |       44 | 0.0% |   0.0% |    - | 15.2% |   0.2500 |
|      ALL |  126 |   53.9 | 12.7% | 0.454 | 0.1 |      122 | 56.2% |  21.9% | 1.7× | 8.6% |   0.3361 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   55 |   12.2 | 10.9% | 0.490 | 0.1 |       52 | 66.7% |  36.4% | 3.1× | 4.9% |   0.2115 |
|       OK |   27 |   37.1 | 0.0% | 0.331 | 0.0 |       26 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   44 |  116.4 | 0.0% | 0.351 | 0.0 |       44 |    - |   0.0% |    - | 0.0% |   0.0682 |
|      ALL |  126 |   53.9 | 4.8% | 0.407 | 0.1 |      122 | 66.7% |  28.6% | 5.8× | 1.8% |   0.1148 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   55 |   12.2 | 10.9% | 0.352 | 0.1 |       52 | 16.7% |  20.0% | 1.7× | 10.6% |   0.0962 |
|       OK |   27 |   37.1 | 7.4% | 0.315 | 0.1 |       26 | 0.0% |      - |    - | 7.7% |   0.0000 |
| DEGRADED |   44 |  116.4 | 6.8% | 0.310 | 0.1 |       44 | 0.0% |   0.0% |    - | 7.0% |   0.0227 |
|      ALL |  126 |   53.9 | 8.7% | 0.329 | 0.1 |      122 | 9.1% |  16.7% | 1.9× | 8.6% |   0.0492 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   17 |   10.2 | 35.3% | 0.613 | 0.5 |       14 | 83.3% |  55.6% | 1.3× | 20.0% |   0.6429 |
|       OK |    4 |   36.0 | 0.0% | 0.397 | 0.0 |        3 |    - |   0.0% |    - | 0.0% |   0.3333 |
| DEGRADED |   10 |  111.0 | 10.0% | 0.515 | 0.1 |       10 | 0.0% |   0.0% |    - | 12.5% |   0.2000 |
|      ALL |   31 |   46.0 | 22.6% | 0.553 | 0.3 |       27 | 71.4% |  41.7% | 1.6× | 13.3% |   0.4444 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   17 |   10.2 | 29.4% | 0.594 | 0.3 |       14 | 60.0% |  50.0% | 1.4× | 25.0% |   0.4286 |
|       OK |    4 |   36.0 | 0.0% | 0.338 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   10 |  111.0 | 0.0% | 0.456 | 0.0 |       10 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   46.0 | 16.1% | 0.517 | 0.2 |       27 | 60.0% |  50.0% | 2.7× | 9.5% |   0.2222 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   17 |   10.2 | 23.5% | 0.515 | 0.2 |       14 | 25.0% |  50.0% | 1.8× | 25.0% |   0.1429 |
|       OK |    4 |   36.0 | 0.0% | 0.316 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   10 |  111.0 | 10.0% | 0.473 | 0.1 |       10 | 0.0% |      - |    - | 10.0% |   0.0000 |
|      ALL |   31 |   46.0 | 16.1% | 0.476 | 0.2 |       27 | 20.0% |  50.0% | 2.7× | 16.0% |   0.0741 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available