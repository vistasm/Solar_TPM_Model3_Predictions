# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-08-30 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (75.0%) is 58.3% HIGHER than DEGRADED (16.7%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (10.0%) is 2.4× the overall rate (4.1%) — score distribution shift detected
🟢 **X+**: FRESH precision (16.7%) is 16.7% HIGHER than DEGRADED (0.0%) — fresher data is helping

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   70 |   12.5 | 24.3% | 0.528 | 0.3 |       69 | 75.0% |  36.4% | 1.6× | 11.1% |   0.4783 |
|       OK |   36 |   37.0 | 13.9% | 0.426 | 0.1 |       35 | 50.0% |  40.0% | 3.5× | 6.7% |   0.1429 |
| DEGRADED |   64 |  115.8 | 9.4% | 0.406 | 0.1 |       62 | 16.7% |   6.7% | 0.7× | 10.6% |   0.2419 |
|      ALL |  170 |   56.6 | 16.5% | 0.460 | 0.2 |      166 | 57.7% |  28.3% | 1.8× | 9.7% |   0.3193 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   70 |   12.5 | 10.0% | 0.520 | 0.1 |       69 | 57.1% |  30.8% | 3.0× | 5.4% |   0.1884 |
|       OK |   36 |   37.0 | 0.0% | 0.364 | 0.0 |       35 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   64 |  115.8 | 0.0% | 0.338 | 0.0 |       62 |    - |   0.0% |    - | 0.0% |   0.0484 |
|      ALL |  170 |   56.6 | 4.1% | 0.418 | 0.0 |      166 | 57.1% |  25.0% | 5.9× | 2.0% |   0.0964 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   70 |   12.5 | 8.6% | 0.374 | 0.1 |       69 | 16.7% |  20.0% | 2.3× | 7.8% |   0.0725 |
|       OK |   36 |   37.0 | 5.6% | 0.322 | 0.1 |       35 | 0.0% |      - |    - | 5.7% |   0.0000 |
| DEGRADED |   64 |  115.8 | 4.7% | 0.287 | 0.1 |       62 | 0.0% |   0.0% |    - | 4.9% |   0.0161 |
|      ALL |  170 |   56.6 | 6.5% | 0.330 | 0.1 |      166 | 9.1% |  16.7% | 2.5× | 6.2% |   0.0361 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   13.3 | 66.7% | 0.648 | 0.9 |        8 | 60.0% |  75.0% | 1.2× | 50.0% |   0.5000 |
|       OK |    5 |   39.0 | 80.0% | 0.652 | 0.8 |        4 | 33.3% | 100.0% | 1.3× | 66.7% |   0.2500 |
| DEGRADED |   14 |  126.0 | 7.1% | 0.372 | 0.1 |       12 | 100.0% | 100.0% | 12.0× | 0.0% |   0.0833 |
|      ALL |   28 |   74.2 | 39.3% | 0.511 | 0.5 |       24 | 55.6% |  83.3% | 2.2× | 22.2% |   0.2500 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   13.3 | 0.0% | 0.674 | 0.0 |        8 |    - |   0.0% |    - | 0.0% |   0.2500 |
|       OK |    5 |   39.0 | 0.0% | 0.643 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   14 |  126.0 | 0.0% | 0.338 | 0.0 |       12 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   28 |   74.2 | 0.0% | 0.501 | 0.0 |       24 |    - |   0.0% |    - | 0.0% |   0.0833 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   13.3 | 0.0% | 0.498 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    5 |   39.0 | 0.0% | 0.380 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   14 |  126.0 | 0.0% | 0.239 | 0.0 |       12 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   28 |   74.2 | 0.0% | 0.348 | 0.0 |       24 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available