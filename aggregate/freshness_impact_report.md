# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-07-03 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (75.0%) is 75.0% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (6.5%) is 2.5× the overall rate (2.6%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   46 |   12.2 | 15.2% | 0.479 | 0.2 |       42 | 75.0% |  15.8% | 1.7× | 4.3% |   0.4524 |
|       OK |   25 |   37.2 | 4.0% | 0.396 | 0.0 |       25 | 100.0% |  33.3% | 8.3× | 0.0% |   0.1200 |
| DEGRADED |   44 |  116.4 | 11.4% | 0.423 | 0.1 |       44 | 0.0% |   0.0% |    - | 15.2% |   0.2500 |
|      ALL |  115 |   57.5 | 11.3% | 0.440 | 0.1 |      111 | 40.0% |  12.1% | 1.4× | 7.7% |   0.2973 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   46 |   12.2 | 6.5% | 0.466 | 0.1 |       42 | 100.0% |  16.7% | 7.0× | 0.0% |   0.1429 |
|       OK |   25 |   37.2 | 0.0% | 0.323 | 0.0 |       25 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   44 |  116.4 | 0.0% | 0.351 | 0.0 |       44 |    - |   0.0% |    - | 0.0% |   0.0682 |
|      ALL |  115 |   57.5 | 2.6% | 0.391 | 0.0 |      111 | 100.0% |  11.1% | 12.3× | 0.0% |   0.0811 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   46 |   12.2 | 6.5% | 0.324 | 0.1 |       42 | 0.0% |   0.0% |    - | 5.1% |   0.0714 |
|       OK |   25 |   37.2 | 8.0% | 0.305 | 0.1 |       25 | 0.0% |      - |    - | 8.0% |   0.0000 |
| DEGRADED |   44 |  116.4 | 6.8% | 0.310 | 0.1 |       44 | 0.0% |   0.0% |    - | 7.0% |   0.0227 |
|      ALL |  115 |   57.5 | 7.0% | 0.314 | 0.1 |      111 | 0.0% |   0.0% |    - | 6.5% |   0.0360 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |   10.4 | 26.7% | 0.544 | 0.3 |       11 | 0.0% |   0.0% |    - | 14.3% |   0.3636 |
|       OK |    5 |   40.2 | 0.0% | 0.367 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   11 |  106.6 | 9.1% | 0.537 | 0.1 |       11 | 0.0% |   0.0% |    - | 11.1% |   0.1818 |
|      ALL |   31 |   49.3 | 16.1% | 0.513 | 0.2 |       27 | 0.0% |   0.0% |    - | 9.5% |   0.2222 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |   10.4 | 13.3% | 0.554 | 0.1 |       11 |    - |   0.0% |    - | 0.0% |   0.1818 |
|       OK |    5 |   40.2 | 0.0% | 0.284 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   11 |  106.6 | 0.0% | 0.474 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   49.3 | 6.5% | 0.482 | 0.1 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |   10.4 | 13.3% | 0.495 | 0.1 |       11 | 0.0% |   0.0% |    - | 10.0% |   0.0909 |
|       OK |    5 |   40.2 | 20.0% | 0.337 | 0.2 |        5 | 0.0% |      - |    - | 20.0% |   0.0000 |
| DEGRADED |   11 |  106.6 | 18.2% | 0.519 | 0.2 |       11 | 0.0% |      - |    - | 18.2% |   0.0000 |
|      ALL |   31 |   49.3 | 16.1% | 0.478 | 0.2 |       27 | 0.0% |   0.0% |    - | 15.4% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available