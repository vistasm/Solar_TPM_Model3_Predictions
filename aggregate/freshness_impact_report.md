# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-05-16 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (100.0%) is 100.0% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (3.7%) is 2.5× the overall rate (1.5%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   27 |   12.6 | 11.1% | 0.472 | 0.1 |       26 | 100.0% |  21.4% | 1.9× | 0.0% |   0.5385 |
|       OK |   16 |   35.7 | 6.2% | 0.406 | 0.1 |       15 | 100.0% |  33.3% | 5.0× | 0.0% |   0.2000 |
| DEGRADED |   24 |  128.9 | 8.3% | 0.371 | 0.1 |       22 | 0.0% |   0.0% |    - | 11.8% |   0.2273 |
|      ALL |   67 |   59.8 | 9.0% | 0.420 | 0.1 |       63 | 66.7% |  18.2% | 1.9× | 4.9% |   0.3492 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   27 |   12.6 | 3.7% | 0.458 | 0.0 |       26 | 100.0% |  25.0% | 6.5× | 0.0% |   0.1538 |
|       OK |   16 |   35.7 | 0.0% | 0.352 | 0.0 |       15 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   24 |  128.9 | 0.0% | 0.312 | 0.0 |       22 |    - |   0.0% |    - | 0.0% |   0.0909 |
|      ALL |   67 |   59.8 | 1.5% | 0.381 | 0.0 |       63 | 100.0% |  16.7% | 10.5× | 0.0% |   0.0952 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   27 |   12.6 | 3.7% | 0.249 | 0.0 |       26 | 0.0% |   0.0% |    - | 4.2% |   0.0769 |
|       OK |   16 |   35.7 | 6.2% | 0.287 | 0.1 |       15 | 0.0% |      - |    - | 6.7% |   0.0000 |
| DEGRADED |   24 |  128.9 | 4.2% | 0.217 | 0.0 |       22 | 0.0% |   0.0% |    - | 4.8% |   0.0455 |
|      ALL |   67 |   59.8 | 4.5% | 0.247 | 0.0 |       63 | 0.0% |   0.0% |    - | 5.0% |   0.0476 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   11.2 | 27.3% | 0.576 | 0.3 |       10 | 100.0% |  50.0% | 1.7× | 0.0% |   0.6000 |
|       OK |    5 |   35.8 | 0.0% | 0.335 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   14 |  157.0 | 0.0% | 0.380 | 0.0 |       12 |    - |   0.0% |    - | 0.0% |   0.3333 |
|      ALL |   30 |   83.4 | 10.0% | 0.444 | 0.1 |       26 | 100.0% |  30.0% | 2.6× | 0.0% |   0.3846 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   11.2 | 9.1% | 0.580 | 0.1 |       10 | 100.0% |  50.0% | 5.0× | 0.0% |   0.2000 |
|       OK |    5 |   35.8 | 0.0% | 0.275 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   14 |  157.0 | 0.0% | 0.324 | 0.0 |       12 |    - |   0.0% |    - | 0.0% |   0.1667 |
|      ALL |   30 |   83.4 | 3.3% | 0.409 | 0.0 |       26 | 100.0% |  25.0% | 6.5× | 0.0% |   0.1538 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   11.2 | 0.0% | 0.275 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.1000 |
|       OK |    5 |   35.8 | 0.0% | 0.134 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   14 |  157.0 | 0.0% | 0.161 | 0.0 |       12 |    - |   0.0% |    - | 0.0% |   0.0833 |
|      ALL |   30 |   83.4 | 0.0% | 0.198 | 0.0 |       26 |    - |   0.0% |    - | 0.0% |   0.0769 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available