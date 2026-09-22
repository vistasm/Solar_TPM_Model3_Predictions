# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-09-22 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (72.2%) is 55.5% HIGHER than DEGRADED (16.7%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (8.9%) is 2.4× the overall rate (3.7%) — score distribution shift detected
🟢 **X+**: FRESH precision (14.3%) is 14.3% HIGHER than DEGRADED (0.0%) — fresher data is helping

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   79 |   12.7 | 22.8% | 0.507 | 0.3 |       78 | 72.2% |  36.1% | 1.6× | 11.9% |   0.4615 |
|       OK |   41 |   36.8 | 12.2% | 0.414 | 0.1 |       40 | 40.0% |  40.0% | 3.2× | 8.6% |   0.1250 |
| DEGRADED |   71 |  118.7 | 8.5% | 0.394 | 0.1 |       69 | 16.7% |   6.7% | 0.8× | 9.3% |   0.2174 |
|      ALL |  191 |   57.3 | 15.2% | 0.445 | 0.2 |      187 | 55.2% |  28.6% | 1.8× | 9.9% |   0.2995 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   79 |   12.7 | 8.9% | 0.492 | 0.1 |       78 | 57.1% |  30.8% | 3.4× | 4.6% |   0.1667 |
|       OK |   41 |   36.8 | 0.0% | 0.347 | 0.0 |       40 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   71 |  118.7 | 0.0% | 0.321 | 0.0 |       69 |    - |   0.0% |    - | 0.0% |   0.0435 |
|      ALL |  191 |   57.3 | 3.7% | 0.397 | 0.0 |      187 | 57.1% |  25.0% | 6.7× | 1.8% |   0.0856 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   79 |   12.7 | 8.9% | 0.373 | 0.1 |       78 | 14.3% |  20.0% | 2.2× | 8.2% |   0.0641 |
|       OK |   41 |   36.8 | 4.9% | 0.316 | 0.1 |       40 | 0.0% |      - |    - | 5.0% |   0.0000 |
| DEGRADED |   71 |  118.7 | 4.2% | 0.270 | 0.0 |       69 | 0.0% |   0.0% |    - | 4.4% |   0.0145 |
|      ALL |  191 |   57.3 | 6.3% | 0.322 | 0.1 |      187 | 8.3% |  16.7% | 2.6× | 6.1% |   0.0321 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   13.0 | 33.3% | 0.440 | 0.3 |       11 | 75.0% |  60.0% | 1.6× | 16.7% |   0.4545 |
|       OK |    7 |   36.0 | 28.6% | 0.430 | 0.3 |        6 | 0.0% |      - |    - | 33.3% |   0.0000 |
| DEGRADED |   10 |  122.5 | 10.0% | 0.322 | 0.1 |        8 | 100.0% | 100.0% | 8.0× | 0.0% |   0.1250 |
|      ALL |   29 |   56.3 | 24.1% | 0.397 | 0.2 |       25 | 57.1% |  66.7% | 2.4× | 15.8% |   0.2400 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   13.0 | 0.0% | 0.401 | 0.0 |       11 |    - |   0.0% |    - | 0.0% |   0.0909 |
|       OK |    7 |   36.0 | 0.0% | 0.365 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   10 |  122.5 | 0.0% | 0.223 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   29 |   56.3 | 0.0% | 0.331 | 0.0 |       25 |    - |   0.0% |    - | 0.0% |   0.0400 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   13.0 | 8.3% | 0.370 | 0.1 |       11 | 0.0% |      - |    - | 9.1% |   0.0000 |
|       OK |    7 |   36.0 | 0.0% | 0.317 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   10 |  122.5 | 0.0% | 0.143 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   29 |   56.3 | 3.5% | 0.279 | 0.0 |       25 | 0.0% |      - |    - | 4.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available