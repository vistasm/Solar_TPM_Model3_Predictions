# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-07-29 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (81.8%) is 81.8% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (11.5%) is 2.3× the overall rate (5.0%) — score distribution shift detected
🟢 **X+**: FRESH precision (16.7%) is 16.7% HIGHER than DEGRADED (0.0%) — fresher data is helping

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   61 |   12.4 | 18.0% | 0.510 | 0.2 |       60 | 81.8% |  31.0% | 1.7× | 6.5% |   0.4833 |
|       OK |   31 |   36.7 | 3.2% | 0.389 | 0.0 |       29 | 100.0% |  25.0% | 7.2× | 0.0% |   0.1379 |
| DEGRADED |   49 |  114.1 | 10.2% | 0.412 | 0.1 |       48 | 0.0% |   0.0% |    - | 13.9% |   0.2500 |
|      ALL |  141 |   53.1 | 12.1% | 0.450 | 0.1 |      137 | 58.8% |  22.2% | 1.8× | 7.6% |   0.3285 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   61 |   12.4 | 11.5% | 0.497 | 0.1 |       60 | 57.1% |  36.4% | 3.1× | 6.1% |   0.1833 |
|       OK |   31 |   36.7 | 0.0% | 0.319 | 0.0 |       29 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   49 |  114.1 | 0.0% | 0.334 | 0.0 |       48 |    - |   0.0% |    - | 0.0% |   0.0625 |
|      ALL |  141 |   53.1 | 5.0% | 0.402 | 0.1 |      137 | 57.1% |  28.6% | 5.6× | 2.4% |   0.1022 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   61 |   12.4 | 9.8% | 0.356 | 0.1 |       60 | 16.7% |  20.0% | 2.0× | 9.1% |   0.0833 |
|       OK |   31 |   36.7 | 6.5% | 0.312 | 0.1 |       29 | 0.0% |      - |    - | 6.9% |   0.0000 |
| DEGRADED |   49 |  114.1 | 6.1% | 0.300 | 0.1 |       48 | 0.0% |   0.0% |    - | 6.4% |   0.0208 |
|      ALL |  141 |   53.1 | 7.8% | 0.327 | 0.1 |      137 | 9.1% |  16.7% | 2.1× | 7.6% |   0.0438 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   19 |   11.4 | 36.8% | 0.655 | 0.5 |       18 | 85.7% |  60.0% | 1.5× | 12.5% |   0.5556 |
|       OK |    6 |   34.4 | 0.0% | 0.362 | 0.0 |        4 |    - |   0.0% |    - | 0.0% |   0.2500 |
| DEGRADED |    6 |  107.4 | 0.0% | 0.338 | 0.0 |        5 |    - |   0.0% |    - | 0.0% |   0.4000 |
|      ALL |   31 |   34.4 | 22.6% | 0.537 | 0.3 |       27 | 85.7% |  46.2% | 1.8× | 7.1% |   0.4815 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   19 |   11.4 | 31.6% | 0.654 | 0.3 |       18 | 50.0% |  60.0% | 1.8× | 23.1% |   0.2778 |
|       OK |    6 |   34.4 | 0.0% | 0.306 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    6 |  107.4 | 0.0% | 0.236 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   34.4 | 19.4% | 0.506 | 0.2 |       27 | 50.0% |  60.0% | 2.7× | 13.6% |   0.1852 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   19 |   11.4 | 21.1% | 0.515 | 0.2 |       18 | 25.0% |  50.0% | 2.2× | 18.8% |   0.1111 |
|       OK |    6 |   34.4 | 0.0% | 0.343 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    6 |  107.4 | 0.0% | 0.216 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   34.4 | 12.9% | 0.424 | 0.1 |       27 | 25.0% |  50.0% | 3.4× | 12.0% |   0.0741 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available