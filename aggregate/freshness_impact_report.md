# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-07-09 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (88.9%) is 88.9% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (11.8%) is 2.4× the overall rate (5.0%) — score distribution shift detected
🟢 **X+**: FRESH precision (20.0%) is 20.0% HIGHER than DEGRADED (0.0%) — fresher data is helping

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   51 |   11.9 | 19.6% | 0.505 | 0.2 |       48 | 88.9% |  32.0% | 1.7× | 4.3% |   0.5208 |
|       OK |   26 |   36.7 | 3.9% | 0.401 | 0.0 |       25 | 100.0% |  33.3% | 8.3× | 0.0% |   0.1200 |
| DEGRADED |   44 |  116.4 | 11.4% | 0.423 | 0.1 |       44 | 0.0% |   0.0% |    - | 15.2% |   0.2500 |
|      ALL |  121 |   55.2 | 13.2% | 0.453 | 0.1 |      117 | 60.0% |  23.1% | 1.8× | 7.7% |   0.3333 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   51 |   11.9 | 11.8% | 0.491 | 0.1 |       48 | 80.0% |  36.4% | 3.5× | 2.7% |   0.2292 |
|       OK |   26 |   36.7 | 0.0% | 0.334 | 0.0 |       25 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   44 |  116.4 | 0.0% | 0.351 | 0.0 |       44 |    - |   0.0% |    - | 0.0% |   0.0682 |
|      ALL |  121 |   55.2 | 5.0% | 0.407 | 0.1 |      117 | 80.0% |  28.6% | 6.7× | 1.0% |   0.1197 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   51 |   11.9 | 11.8% | 0.356 | 0.1 |       48 | 20.0% |  20.0% | 1.9× | 9.3% |   0.1042 |
|       OK |   26 |   36.7 | 7.7% | 0.317 | 0.1 |       25 | 0.0% |      - |    - | 8.0% |   0.0000 |
| DEGRADED |   44 |  116.4 | 6.8% | 0.310 | 0.1 |       44 | 0.0% |   0.0% |    - | 7.0% |   0.0227 |
|      ALL |  121 |   55.2 | 9.1% | 0.331 | 0.1 |      117 | 10.0% |  16.7% | 1.9× | 8.1% |   0.0513 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   16 |    9.2 | 43.8% | 0.634 | 0.6 |       13 | 83.3% |  62.5% | 1.4× | 20.0% |   0.6154 |
|       OK |    4 |   35.9 | 0.0% | 0.372 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   11 |  106.6 | 9.1% | 0.537 | 0.1 |       11 | 0.0% |   0.0% |    - | 11.1% |   0.1818 |
|      ALL |   31 |   47.2 | 25.8% | 0.566 | 0.3 |       27 | 71.4% |  50.0% | 1.9× | 11.8% |   0.3704 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   16 |    9.2 | 31.2% | 0.630 | 0.3 |       13 | 75.0% |  50.0% | 1.6× | 14.3% |   0.4615 |
|       OK |    4 |   35.9 | 0.0% | 0.331 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   11 |  106.6 | 0.0% | 0.474 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   47.2 | 16.1% | 0.536 | 0.2 |       27 | 75.0% |  50.0% | 3.4× | 4.8% |   0.2222 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   16 |    9.2 | 31.2% | 0.597 | 0.3 |       13 | 25.0% |  50.0% | 1.6× | 27.3% |   0.1538 |
|       OK |    4 |   35.9 | 0.0% | 0.283 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   11 |  106.6 | 18.2% | 0.519 | 0.2 |       11 | 0.0% |      - |    - | 18.2% |   0.0000 |
|      ALL |   31 |   47.2 | 22.6% | 0.529 | 0.2 |       27 | 16.7% |  50.0% | 2.2× | 20.0% |   0.0741 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available