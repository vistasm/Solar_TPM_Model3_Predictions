# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-11-15 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (66.7%) is 28.2% HIGHER than DEGRADED (38.5%) — fresher data is helping
🟢 **X+**: FRESH precision (14.3%) is 14.3% HIGHER than DEGRADED (0.0%) — fresher data is helping

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   84 |   12.5 | 25.0% | 0.523 | 0.3 |       82 | 66.7% |  37.8% | 1.5× | 15.6% |   0.4512 |
|       OK |   44 |   36.6 | 15.9% | 0.439 | 0.2 |       43 | 42.9% |  50.0% | 3.1× | 10.8% |   0.1395 |
| DEGRADED |  123 |  115.8 | 10.6% | 0.404 | 0.1 |      122 | 38.5% |  20.8% | 2.0× | 8.2% |   0.1967 |
|      ALL |  251 |   67.3 | 16.3% | 0.450 | 0.2 |      247 | 53.7% |  32.8% | 2.0× | 10.6% |   0.2713 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   84 |   12.5 | 11.9% | 0.510 | 0.1 |       82 | 40.0% |  30.8% | 2.5× | 8.7% |   0.1585 |
|       OK |   44 |   36.6 | 4.5% | 0.378 | 0.1 |       43 | 0.0% |      - |    - | 4.7% |   0.0000 |
| DEGRADED |  123 |  115.8 | 4.1% | 0.346 | 0.0 |      122 | 40.0% |  40.0% | 9.8× | 2.6% |   0.0410 |
|      ALL |  251 |   67.3 | 6.8% | 0.406 | 0.1 |      247 | 35.3% |  33.3% | 4.8× | 4.8% |   0.0729 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   84 |   12.5 | 9.5% | 0.395 | 0.1 |       82 | 14.3% |  20.0% | 2.3× | 7.8% |   0.0610 |
|       OK |   44 |   36.6 | 4.5% | 0.339 | 0.1 |       43 | 0.0% |      - |    - | 4.7% |   0.0000 |
| DEGRADED |  123 |  115.8 | 4.1% | 0.277 | 0.0 |      122 | 0.0% |   0.0% |    - | 4.1% |   0.0082 |
|      ALL |  251 |   67.3 | 6.0% | 0.328 | 0.1 |      247 | 7.1% |  16.7% | 2.9× | 5.4% |   0.0243 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    5 |    9.8 | 60.0% | 0.789 | 0.6 |        3 | 33.3% | 100.0% | 1.0× | 100.0% |   0.3333 |
|       OK |    3 |   34.1 | 66.7% | 0.778 | 0.7 |        2 | 50.0% | 100.0% | 1.0× | 100.0% |   0.5000 |
| DEGRADED |   23 |  112.1 | 4.3% | 0.368 | 0.0 |       22 | 100.0% |  25.0% | 5.5× | 0.0% |   0.1818 |
|      ALL |   31 |   88.1 | 19.4% | 0.475 | 0.2 |       27 | 50.0% |  50.0% | 2.2× | 14.3% |   0.2222 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    5 |    9.8 | 60.0% | 0.796 | 0.6 |        3 | 0.0% |      - |    - | 100.0% |   0.0000 |
|       OK |    3 |   34.1 | 66.7% | 0.788 | 0.7 |        2 | 0.0% |      - |    - | 100.0% |   0.0000 |
| DEGRADED |   23 |  112.1 | 4.3% | 0.346 | 0.0 |       22 | 0.0% |      - |    - | 4.5% |   0.0000 |
|      ALL |   31 |   88.1 | 19.4% | 0.461 | 0.2 |       27 | 0.0% |      - |    - | 22.2% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    5 |    9.8 | 20.0% | 0.740 | 0.2 |        3 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    3 |   34.1 | 0.0% | 0.664 | 0.0 |        2 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   23 |  112.1 | 0.0% | 0.252 | 0.0 |       22 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   88.1 | 3.2% | 0.370 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available