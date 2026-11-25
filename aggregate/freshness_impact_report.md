# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-11-25 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (66.7%) is 28.2% HIGHER than DEGRADED (38.5%) — fresher data is helping
🟢 **X+**: FRESH precision (12.5%) is 12.5% HIGHER than DEGRADED (0.0%) — fresher data is helping

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   87 |   12.5 | 24.1% | 0.525 | 0.3 |       87 | 66.7% |  36.8% | 1.5× | 14.3% |   0.4368 |
|       OK |   47 |   36.3 | 14.9% | 0.433 | 0.1 |       47 | 42.9% |  42.9% | 2.9× | 10.0% |   0.1489 |
| DEGRADED |  127 |  115.2 | 10.2% | 0.396 | 0.1 |      123 | 38.5% |  20.8% | 2.0× | 8.1% |   0.1951 |
|      ALL |  261 |   66.8 | 15.7% | 0.446 | 0.2 |      257 | 53.7% |  31.9% | 2.0× | 10.1% |   0.2685 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   87 |   12.5 | 11.5% | 0.508 | 0.1 |       87 | 40.0% |  30.8% | 2.7× | 8.1% |   0.1494 |
|       OK |   47 |   36.3 | 4.3% | 0.372 | 0.0 |       47 | 0.0% |      - |    - | 4.3% |   0.0000 |
| DEGRADED |  127 |  115.2 | 3.9% | 0.338 | 0.0 |      123 | 40.0% |  40.0% | 9.8× | 2.5% |   0.0406 |
|      ALL |  261 |   66.8 | 6.5% | 0.401 | 0.1 |      257 | 35.3% |  33.3% | 5.0× | 4.6% |   0.0700 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   87 |   12.5 | 9.2% | 0.394 | 0.1 |       87 | 12.5% |  20.0% | 2.2× | 8.5% |   0.0575 |
|       OK |   47 |   36.3 | 4.3% | 0.329 | 0.0 |       47 | 0.0% |      - |    - | 4.3% |   0.0000 |
| DEGRADED |  127 |  115.2 | 3.9% | 0.270 | 0.0 |      123 | 0.0% |   0.0% |    - | 4.1% |   0.0081 |
|      ALL |  261 |   66.8 | 5.8% | 0.322 | 0.1 |      257 | 6.7% |  16.7% | 2.9× | 5.6% |   0.0233 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   10.7 | 37.5% | 0.709 | 0.4 |        8 | 33.3% |  50.0% | 1.3× | 33.3% |   0.2500 |
|       OK |    6 |   33.2 | 33.3% | 0.559 | 0.3 |        6 | 50.0% |  50.0% | 1.5× | 25.0% |   0.3333 |
| DEGRADED |   17 |  117.8 | 5.9% | 0.287 | 0.1 |       13 | 100.0% |  50.0% | 6.5× | 0.0% |   0.1538 |
|      ALL |   31 |   73.8 | 19.4% | 0.449 | 0.2 |       27 | 50.0% |  50.0% | 2.2× | 14.3% |   0.2222 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   10.7 | 37.5% | 0.663 | 0.4 |        8 | 0.0% |      - |    - | 37.5% |   0.0000 |
|       OK |    6 |   33.2 | 33.3% | 0.540 | 0.3 |        6 | 0.0% |      - |    - | 33.3% |   0.0000 |
| DEGRADED |   17 |  117.8 | 5.9% | 0.204 | 0.1 |       13 | 0.0% |      - |    - | 7.7% |   0.0000 |
|      ALL |   31 |   73.8 | 19.4% | 0.388 | 0.2 |       27 | 0.0% |      - |    - | 22.2% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   10.7 | 12.5% | 0.606 | 0.1 |        8 | 0.0% |      - |    - | 12.5% |   0.0000 |
|       OK |    6 |   33.2 | 0.0% | 0.424 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   17 |  117.8 | 0.0% | 0.184 | 0.0 |       13 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   73.8 | 3.2% | 0.340 | 0.0 |       27 | 0.0% |      - |    - | 3.7% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available