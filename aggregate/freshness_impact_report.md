# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-07-31 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (81.8%) is 81.8% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (11.3%) is 2.3× the overall rate (4.9%) — score distribution shift detected
🟢 **X+**: FRESH precision (16.7%) is 16.7% HIGHER than DEGRADED (0.0%) — fresher data is helping

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   62 |   12.4 | 17.7% | 0.510 | 0.2 |       61 | 81.8% |  31.0% | 1.7× | 6.2% |   0.4754 |
|       OK |   31 |   36.7 | 3.2% | 0.389 | 0.0 |       29 | 100.0% |  25.0% | 7.2× | 0.0% |   0.1379 |
| DEGRADED |   50 |  112.9 | 10.0% | 0.415 | 0.1 |       49 | 0.0% |   0.0% |    - | 13.9% |   0.2653 |
|      ALL |  143 |   52.8 | 11.9% | 0.451 | 0.1 |      139 | 58.8% |  21.7% | 1.8× | 7.5% |   0.3309 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   62 |   12.4 | 11.3% | 0.498 | 0.1 |       61 | 57.1% |  36.4% | 3.2× | 6.0% |   0.1803 |
|       OK |   31 |   36.7 | 0.0% | 0.319 | 0.0 |       29 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   50 |  112.9 | 0.0% | 0.338 | 0.0 |       49 |    - |   0.0% |    - | 0.0% |   0.0612 |
|      ALL |  143 |   52.8 | 4.9% | 0.404 | 0.1 |      139 | 57.1% |  28.6% | 5.7× | 2.4% |   0.1007 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   62 |   12.4 | 9.7% | 0.357 | 0.1 |       61 | 16.7% |  20.0% | 2.0× | 8.9% |   0.0820 |
|       OK |   31 |   36.7 | 6.5% | 0.312 | 0.1 |       29 | 0.0% |      - |    - | 6.9% |   0.0000 |
| DEGRADED |   50 |  112.9 | 6.0% | 0.300 | 0.1 |       49 | 0.0% |   0.0% |    - | 6.2% |   0.0204 |
|      ALL |  143 |   52.8 | 7.7% | 0.328 | 0.1 |      139 | 9.1% |  16.7% | 2.1× | 7.5% |   0.0432 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   19 |   11.8 | 36.8% | 0.648 | 0.5 |       18 | 85.7% |  66.7% | 1.7× | 11.1% |   0.5000 |
|       OK |    6 |   34.4 | 0.0% | 0.362 | 0.0 |        4 |    - |   0.0% |    - | 0.0% |   0.2500 |
| DEGRADED |    6 |   86.8 | 0.0% | 0.358 | 0.0 |        5 |    - |   0.0% |    - | 0.0% |   0.4000 |
|      ALL |   31 |   30.7 | 22.6% | 0.537 | 0.3 |       27 | 85.7% |  50.0% | 1.9× | 6.7% |   0.4444 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   19 |   11.8 | 31.6% | 0.645 | 0.3 |       18 | 50.0% |  75.0% | 2.2× | 21.4% |   0.2222 |
|       OK |    6 |   34.4 | 0.0% | 0.306 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    6 |   86.8 | 0.0% | 0.241 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   30.7 | 19.4% | 0.501 | 0.2 |       27 | 50.0% |  75.0% | 3.4× | 13.0% |   0.1481 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   19 |   11.8 | 21.1% | 0.512 | 0.2 |       18 | 25.0% | 100.0% | 4.5× | 17.6% |   0.0556 |
|       OK |    6 |   34.4 | 0.0% | 0.343 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    6 |   86.8 | 0.0% | 0.229 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   30.7 | 12.9% | 0.424 | 0.1 |       27 | 25.0% | 100.0% | 6.8× | 11.5% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available