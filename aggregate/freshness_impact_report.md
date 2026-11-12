# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-11-12 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (70.0%) is 36.7% HIGHER than DEGRADED (33.3%) — fresher data is helping
🟢 **X+**: FRESH precision (14.3%) is 14.3% HIGHER than DEGRADED (0.0%) — fresher data is helping

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   83 |   12.6 | 25.3% | 0.522 | 0.3 |       81 | 70.0% |  37.8% | 1.5× | 13.6% |   0.4568 |
|       OK |   43 |   36.7 | 16.3% | 0.436 | 0.2 |       42 | 50.0% |  50.0% | 3.5× | 8.3% |   0.1429 |
| DEGRADED |  122 |  116.2 | 10.7% | 0.405 | 0.1 |      121 | 33.3% |  17.4% | 1.8× | 8.2% |   0.1901 |
|      ALL |  248 |   67.8 | 16.5% | 0.450 | 0.2 |      244 | 55.3% |  31.8% | 2.0× | 9.6% |   0.2705 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   83 |   12.6 | 12.0% | 0.510 | 0.1 |       81 | 44.4% |  30.8% | 2.8× | 7.3% |   0.1605 |
|       OK |   43 |   36.7 | 4.7% | 0.374 | 0.1 |       42 | 0.0% |      - |    - | 2.4% |   0.0000 |
| DEGRADED |  122 |  116.2 | 4.1% | 0.347 | 0.0 |      121 | 50.0% |  40.0% | 12.1× | 1.7% |   0.0413 |
|      ALL |  248 |   67.8 | 6.9% | 0.406 | 0.1 |      244 | 42.9% |  33.3% | 5.8× | 3.5% |   0.0738 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   83 |   12.6 | 8.4% | 0.388 | 0.1 |       81 | 14.3% |  20.0% | 2.3× | 7.9% |   0.0617 |
|       OK |   43 |   36.7 | 4.7% | 0.339 | 0.1 |       42 | 0.0% |      - |    - | 4.8% |   0.0000 |
| DEGRADED |  122 |  116.2 | 4.1% | 0.278 | 0.0 |      121 | 0.0% |   0.0% |    - | 4.2% |   0.0083 |
|      ALL |  248 |   67.8 | 5.7% | 0.325 | 0.1 |      244 | 7.1% |  16.7% | 2.9× | 5.5% |   0.0246 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    4 |   10.2 | 75.0% | 0.830 | 0.8 |        2 | 50.0% | 100.0% | 1.0× | 100.0% |   0.5000 |
|       OK |    2 |   35.0 | 100.0% | 0.893 | 1.0 |        1 | 100.0% | 100.0% | 1.0× |   - |   1.0000 |
| DEGRADED |   25 |  112.6 | 4.0% | 0.392 | 0.0 |       24 |    - |   0.0% |    - | 0.0% |   0.1250 |
|      ALL |   31 |   94.4 | 19.4% | 0.481 | 0.2 |       27 | 66.7% |  40.0% | 3.6× | 4.5% |   0.1852 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    4 |   10.2 | 75.0% | 0.859 | 0.8 |        2 | 0.0% |      - |    - | 100.0% |   0.0000 |
|       OK |    2 |   35.0 | 100.0% | 0.917 | 1.0 |        1 | 0.0% |      - |    - | 100.0% |   0.0000 |
| DEGRADED |   25 |  112.6 | 4.0% | 0.375 | 0.0 |       24 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   94.4 | 19.4% | 0.472 | 0.2 |       27 | 0.0% |      - |    - | 11.1% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    4 |   10.2 | 0.0% | 0.681 | 0.0 |        2 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    2 |   35.0 | 0.0% | 0.817 | 0.0 |        1 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   25 |  112.6 | 0.0% | 0.264 | 0.0 |       24 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   94.4 | 0.0% | 0.353 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available