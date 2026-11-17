# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-11-17 UTC
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
|    FRESH |   85 |   12.5 | 24.7% | 0.523 | 0.3 |       83 | 66.7% |  37.8% | 1.5× | 15.2% |   0.4458 |
|       OK |   45 |   36.5 | 15.6% | 0.437 | 0.2 |       44 | 42.9% |  50.0% | 3.1× | 10.5% |   0.1364 |
| DEGRADED |  123 |  115.8 | 10.6% | 0.404 | 0.1 |      122 | 38.5% |  20.8% | 2.0× | 8.2% |   0.1967 |
|      ALL |  253 |   67.0 | 16.2% | 0.450 | 0.2 |      249 | 53.7% |  32.8% | 2.0× | 10.4% |   0.2691 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   85 |   12.5 | 11.8% | 0.508 | 0.1 |       83 | 40.0% |  30.8% | 2.5× | 8.6% |   0.1566 |
|       OK |   45 |   36.5 | 4.4% | 0.377 | 0.0 |       44 | 0.0% |      - |    - | 4.5% |   0.0000 |
| DEGRADED |  123 |  115.8 | 4.1% | 0.346 | 0.0 |      122 | 40.0% |  40.0% | 9.8× | 2.6% |   0.0410 |
|      ALL |  253 |   67.0 | 6.7% | 0.406 | 0.1 |      249 | 35.3% |  33.3% | 4.9× | 4.8% |   0.0723 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   85 |   12.5 | 9.4% | 0.393 | 0.1 |       83 | 14.3% |  20.0% | 2.4× | 7.7% |   0.0602 |
|       OK |   45 |   36.5 | 4.4% | 0.336 | 0.0 |       44 | 0.0% |      - |    - | 4.5% |   0.0000 |
| DEGRADED |  123 |  115.8 | 4.1% | 0.277 | 0.0 |      122 | 0.0% |   0.0% |    - | 4.1% |   0.0082 |
|      ALL |  253 |   67.0 | 5.9% | 0.326 | 0.1 |      249 | 7.1% |  16.7% | 3.0× | 5.3% |   0.0241 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    6 |   10.4 | 50.0% | 0.746 | 0.5 |        4 | 33.3% | 100.0% | 1.3× | 66.7% |   0.2500 |
|       OK |    4 |   33.6 | 50.0% | 0.670 | 0.5 |        3 | 50.0% | 100.0% | 1.5× | 50.0% |   0.3333 |
| DEGRADED |   21 |  113.5 | 4.8% | 0.350 | 0.1 |       20 | 100.0% |  33.3% | 6.7× | 0.0% |   0.1500 |
|      ALL |   31 |   83.3 | 19.4% | 0.468 | 0.2 |       27 | 50.0% |  60.0% | 2.7× | 13.6% |   0.1852 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    6 |   10.4 | 50.0% | 0.720 | 0.5 |        4 | 0.0% |      - |    - | 75.0% |   0.0000 |
|       OK |    4 |   33.6 | 50.0% | 0.681 | 0.5 |        3 | 0.0% |      - |    - | 66.7% |   0.0000 |
| DEGRADED |   21 |  113.5 | 4.8% | 0.313 | 0.1 |       20 | 0.0% |      - |    - | 5.0% |   0.0000 |
|      ALL |   31 |   83.3 | 19.4% | 0.439 | 0.2 |       27 | 0.0% |      - |    - | 22.2% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    6 |   10.4 | 16.7% | 0.652 | 0.2 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    4 |   33.6 | 0.0% | 0.542 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   21 |  113.5 | 0.0% | 0.246 | 0.0 |       20 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   83.3 | 3.2% | 0.363 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available