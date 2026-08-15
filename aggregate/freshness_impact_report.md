# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-08-15 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (81.8%) is 81.8% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (11.1%) is 2.5× the overall rate (4.5%) — score distribution shift detected
🟢 **X+**: FRESH precision (16.7%) is 16.7% HIGHER than DEGRADED (0.0%) — fresher data is helping

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   63 |   12.6 | 17.5% | 0.510 | 0.2 |       62 | 81.8% |  31.0% | 1.8× | 6.1% |   0.4677 |
|       OK |   32 |   36.7 | 6.2% | 0.402 | 0.1 |       32 | 50.0% |  25.0% | 4.0× | 3.6% |   0.1250 |
| DEGRADED |   61 |  118.1 | 8.2% | 0.406 | 0.1 |       59 | 0.0% |   0.0% |    - | 11.1% |   0.2373 |
|      ALL |  156 |   58.8 | 11.5% | 0.447 | 0.1 |      153 | 55.6% |  21.3% | 1.8× | 7.5% |   0.3072 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   63 |   12.6 | 11.1% | 0.500 | 0.1 |       62 | 57.1% |  36.4% | 3.2× | 5.9% |   0.1774 |
|       OK |   32 |   36.7 | 0.0% | 0.329 | 0.0 |       32 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   61 |  118.1 | 0.0% | 0.337 | 0.0 |       59 |    - |   0.0% |    - | 0.0% |   0.0508 |
|      ALL |  156 |   58.8 | 4.5% | 0.401 | 0.0 |      153 | 57.1% |  28.6% | 6.2× | 2.2% |   0.0915 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   63 |   12.6 | 9.5% | 0.355 | 0.1 |       62 | 16.7% |  20.0% | 2.1× | 8.8% |   0.0806 |
|       OK |   32 |   36.7 | 6.2% | 0.315 | 0.1 |       32 | 0.0% |      - |    - | 6.2% |   0.0000 |
| DEGRADED |   61 |  118.1 | 4.9% | 0.291 | 0.1 |       59 | 0.0% |   0.0% |    - | 5.2% |   0.0169 |
|      ALL |  156 |   58.8 | 7.0% | 0.322 | 0.1 |      153 | 9.1% |  16.7% | 2.3× | 6.8% |   0.0392 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    7 |   15.1 | 14.3% | 0.592 | 0.1 |        6 | 100.0% |  50.0% | 3.0× | 0.0% |   0.3333 |
|       OK |    5 |   34.7 | 20.0% | 0.421 | 0.2 |        5 | 0.0% |      - |    - | 20.0% |   0.0000 |
| DEGRADED |   17 |  122.5 | 0.0% | 0.362 | 0.0 |       15 |    - |   0.0% |    - | 0.0% |   0.2000 |
|      ALL |   29 |   81.4 | 6.9% | 0.428 | 0.1 |       26 | 50.0% |  20.0% | 2.6× | 4.8% |   0.1923 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    7 |   15.1 | 14.3% | 0.634 | 0.1 |        6 | 0.0% |      - |    - | 16.7% |   0.0000 |
|       OK |    5 |   34.7 | 0.0% | 0.321 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   17 |  122.5 | 0.0% | 0.298 | 0.0 |       15 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   29 |   81.4 | 3.5% | 0.383 | 0.0 |       26 | 0.0% |      - |    - | 3.9% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    7 |   15.1 | 0.0% | 0.415 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    5 |   34.7 | 0.0% | 0.315 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   17 |  122.5 | 0.0% | 0.241 | 0.0 |       15 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   29 |   81.4 | 0.0% | 0.296 | 0.0 |       26 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available