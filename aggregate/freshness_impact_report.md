# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-09-09 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (72.2%) is 55.5% HIGHER than DEGRADED (16.7%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (9.1%) is 2.3× the overall rate (3.9%) — score distribution shift detected
🟢 **X+**: FRESH precision (14.3%) is 14.3% HIGHER than DEGRADED (0.0%) — fresher data is helping

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   77 |   12.6 | 23.4% | 0.516 | 0.3 |       74 | 72.2% |  36.1% | 1.5× | 13.2% |   0.4865 |
|       OK |   39 |   36.6 | 12.8% | 0.413 | 0.1 |       38 | 40.0% |  40.0% | 3.0× | 9.1% |   0.1316 |
| DEGRADED |   64 |  115.8 | 9.4% | 0.406 | 0.1 |       64 | 16.7% |   6.7% | 0.7× | 10.2% |   0.2344 |
|      ALL |  180 |   54.5 | 16.1% | 0.455 | 0.2 |      176 | 55.2% |  28.6% | 1.7× | 10.8% |   0.3182 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   77 |   12.6 | 9.1% | 0.503 | 0.1 |       74 | 57.1% |  30.8% | 3.2× | 4.9% |   0.1757 |
|       OK |   39 |   36.6 | 0.0% | 0.350 | 0.0 |       38 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   64 |  115.8 | 0.0% | 0.338 | 0.0 |       64 |    - |   0.0% |    - | 0.0% |   0.0469 |
|      ALL |  180 |   54.5 | 3.9% | 0.411 | 0.0 |      176 | 57.1% |  25.0% | 6.3× | 1.9% |   0.0909 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   77 |   12.6 | 9.1% | 0.381 | 0.1 |       74 | 14.3% |  20.0% | 2.1× | 8.7% |   0.0676 |
|       OK |   39 |   36.6 | 5.1% | 0.307 | 0.1 |       38 | 0.0% |      - |    - | 5.3% |   0.0000 |
| DEGRADED |   64 |  115.8 | 4.7% | 0.287 | 0.1 |       64 | 0.0% |   0.0% |    - | 4.8% |   0.0156 |
|      ALL |  180 |   54.5 | 6.7% | 0.332 | 0.1 |      176 | 8.3% |  16.7% | 2.4× | 6.5% |   0.0341 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |   13.5 | 46.7% | 0.542 | 0.6 |       12 | 57.1% |  57.1% | 1.0× | 60.0% |   0.5833 |
|       OK |    7 |   36.5 | 42.9% | 0.464 | 0.4 |        6 | 33.3% | 100.0% | 2.0× | 40.0% |   0.1667 |
| DEGRADED |    6 |  101.4 | 16.7% | 0.390 | 0.2 |        6 | 100.0% | 100.0% | 6.0× | 0.0% |   0.1667 |
|      ALL |   28 |   38.1 | 39.3% | 0.490 | 0.5 |       24 | 54.5% |  66.7% | 1.4× | 33.3% |   0.3750 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |   13.5 | 0.0% | 0.523 | 0.0 |       12 |    - |   0.0% |    - | 0.0% |   0.1667 |
|       OK |    7 |   36.5 | 0.0% | 0.445 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    6 |  101.4 | 0.0% | 0.353 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   28 |   38.1 | 0.0% | 0.467 | 0.0 |       24 |    - |   0.0% |    - | 0.0% |   0.0833 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |   13.5 | 6.7% | 0.480 | 0.1 |       12 | 0.0% |      - |    - | 8.3% |   0.0000 |
|       OK |    7 |   36.5 | 0.0% | 0.269 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    6 |  101.4 | 0.0% | 0.219 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   28 |   38.1 | 3.6% | 0.371 | 0.0 |       24 | 0.0% |      - |    - | 4.2% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available