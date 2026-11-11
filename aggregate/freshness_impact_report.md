# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-11-11 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (68.4%) is 35.1% HIGHER than DEGRADED (33.3%) — fresher data is helping
🟢 **X+**: FRESH precision (14.3%) is 14.3% HIGHER than DEGRADED (0.0%) — fresher data is helping

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   82 |   12.6 | 25.6% | 0.521 | 0.3 |       80 | 68.4% |  36.1% | 1.5× | 13.6% |   0.4500 |
|       OK |   43 |   36.7 | 16.3% | 0.436 | 0.2 |       42 | 50.0% |  50.0% | 3.5× | 8.3% |   0.1429 |
| DEGRADED |  122 |  116.2 | 10.7% | 0.405 | 0.1 |      121 | 33.3% |  17.4% | 1.8× | 8.2% |   0.1901 |
|      ALL |  247 |   68.0 | 16.6% | 0.449 | 0.2 |      243 | 54.0% |  30.8% | 2.0× | 9.6% |   0.2675 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   82 |   12.6 | 12.2% | 0.507 | 0.1 |       80 | 50.0% |  30.8% | 3.1× | 6.0% |   0.1625 |
|       OK |   43 |   36.7 | 4.7% | 0.374 | 0.1 |       42 | 0.0% |      - |    - | 2.4% |   0.0000 |
| DEGRADED |  122 |  116.2 | 4.1% | 0.347 | 0.0 |      121 | 50.0% |  40.0% | 12.1× | 1.7% |   0.0413 |
|      ALL |  247 |   68.0 | 6.9% | 0.405 | 0.1 |      243 | 46.2% |  33.3% | 6.2× | 3.1% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   82 |   12.6 | 8.5% | 0.388 | 0.1 |       80 | 14.3% |  20.0% | 2.3× | 8.0% |   0.0625 |
|       OK |   43 |   36.7 | 4.7% | 0.339 | 0.1 |       42 | 0.0% |      - |    - | 4.8% |   0.0000 |
| DEGRADED |  122 |  116.2 | 4.1% | 0.278 | 0.0 |      121 | 0.0% |   0.0% |    - | 4.2% |   0.0083 |
|      ALL |  247 |   68.0 | 5.7% | 0.325 | 0.1 |      243 | 7.1% |  16.7% | 2.9× | 5.5% |   0.0247 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    3 |   10.9 | 100.0% | 0.898 | 1.0 |        1 | 0.0% |      - |    - | 100.0% |   0.0000 |
|       OK |    2 |   35.0 | 100.0% | 0.893 | 1.0 |        1 | 100.0% | 100.0% | 1.0× |   - |   1.0000 |
| DEGRADED |   26 |  112.0 | 7.7% | 0.411 | 0.1 |       25 | 0.0% |   0.0% |    - | 4.5% |   0.1200 |
|      ALL |   31 |   97.3 | 22.6% | 0.489 | 0.2 |       27 | 33.3% |  25.0% | 2.2× | 8.7% |   0.1481 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    3 |   10.9 | 100.0% | 0.913 | 1.0 |        1 | 0.0% |      - |    - | 100.0% |   0.0000 |
|       OK |    2 |   35.0 | 100.0% | 0.917 | 1.0 |        1 | 0.0% |      - |    - | 100.0% |   0.0000 |
| DEGRADED |   26 |  112.0 | 7.7% | 0.395 | 0.1 |       25 | 0.0% |      - |    - | 4.0% |   0.0000 |
|      ALL |   31 |   97.3 | 22.6% | 0.479 | 0.2 |       27 | 0.0% |      - |    - | 11.1% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    3 |   10.9 | 0.0% | 0.776 | 0.0 |        1 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    2 |   35.0 | 0.0% | 0.817 | 0.0 |        1 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   26 |  112.0 | 0.0% | 0.281 | 0.0 |       25 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   97.3 | 0.0% | 0.364 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available