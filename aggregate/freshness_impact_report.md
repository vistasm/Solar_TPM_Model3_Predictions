# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-08-31 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (70.6%) is 53.9% HIGHER than DEGRADED (16.7%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (10.0%) is 2.4× the overall rate (4.1%) — score distribution shift detected
🟢 **X+**: FRESH precision (16.7%) is 16.7% HIGHER than DEGRADED (0.0%) — fresher data is helping

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   70 |   12.5 | 24.3% | 0.528 | 0.3 |       70 | 70.6% |  36.4% | 1.5× | 13.5% |   0.4714 |
|       OK |   37 |   36.8 | 13.5% | 0.420 | 0.1 |       35 | 50.0% |  40.0% | 3.5× | 6.7% |   0.1429 |
| DEGRADED |   64 |  115.8 | 9.4% | 0.406 | 0.1 |       62 | 16.7% |   6.7% | 0.7× | 10.6% |   0.2419 |
|      ALL |  171 |   56.4 | 16.4% | 0.459 | 0.2 |      167 | 55.6% |  28.3% | 1.8× | 10.5% |   0.3174 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   70 |   12.5 | 10.0% | 0.520 | 0.1 |       70 | 57.1% |  30.8% | 3.1× | 5.3% |   0.1857 |
|       OK |   37 |   36.8 | 0.0% | 0.356 | 0.0 |       35 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   64 |  115.8 | 0.0% | 0.338 | 0.0 |       62 |    - |   0.0% |    - | 0.0% |   0.0484 |
|      ALL |  171 |   56.4 | 4.1% | 0.416 | 0.0 |      167 | 57.1% |  25.0% | 6.0× | 2.0% |   0.0958 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   70 |   12.5 | 8.6% | 0.374 | 0.1 |       70 | 16.7% |  20.0% | 2.3× | 7.7% |   0.0714 |
|       OK |   37 |   36.8 | 5.4% | 0.314 | 0.1 |       35 | 0.0% |      - |    - | 5.7% |   0.0000 |
| DEGRADED |   64 |  115.8 | 4.7% | 0.287 | 0.1 |       62 | 0.0% |   0.0% |    - | 4.9% |   0.0161 |
|      ALL |  171 |   56.4 | 6.4% | 0.329 | 0.1 |      167 | 9.1% |  16.7% | 2.5× | 6.2% |   0.0359 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   13.4 | 75.0% | 0.665 | 1.0 |        8 | 50.0% |  75.0% | 1.0× | 75.0% |   0.5000 |
|       OK |    6 |   37.2 | 66.7% | 0.581 | 0.7 |        4 | 33.3% | 100.0% | 1.3× | 66.7% |   0.2500 |
| DEGRADED |   14 |  126.0 | 7.1% | 0.372 | 0.1 |       12 | 100.0% | 100.0% | 12.0× | 0.0% |   0.0833 |
|      ALL |   28 |   74.8 | 39.3% | 0.501 | 0.5 |       24 | 50.0% |  83.3% | 2.0× | 27.8% |   0.2500 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   13.4 | 0.0% | 0.687 | 0.0 |        8 |    - |   0.0% |    - | 0.0% |   0.2500 |
|       OK |    6 |   37.2 | 0.0% | 0.548 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   14 |  126.0 | 0.0% | 0.338 | 0.0 |       12 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   28 |   74.8 | 0.0% | 0.483 | 0.0 |       24 |    - |   0.0% |    - | 0.0% |   0.0833 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   13.4 | 0.0% | 0.507 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    6 |   37.2 | 0.0% | 0.325 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   14 |  126.0 | 0.0% | 0.239 | 0.0 |       12 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   28 |   74.8 | 0.0% | 0.334 | 0.0 |       24 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available