# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-05-18 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (100.0%) is 100.0% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (3.6%) is 2.5× the overall rate (1.5%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   28 |   12.4 | 10.7% | 0.471 | 0.1 |       26 | 100.0% |  21.4% | 1.9× | 0.0% |   0.5385 |
|       OK |   17 |   35.1 | 5.9% | 0.394 | 0.1 |       15 | 100.0% |  33.3% | 5.0× | 0.0% |   0.2000 |
| DEGRADED |   24 |  128.9 | 8.3% | 0.371 | 0.1 |       24 | 0.0% |   0.0% |    - | 10.5% |   0.2083 |
|      ALL |   69 |   58.5 | 8.7% | 0.417 | 0.1 |       65 | 66.7% |  18.2% | 2.0× | 4.7% |   0.3385 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   28 |   12.4 | 3.6% | 0.452 | 0.0 |       26 | 100.0% |  25.0% | 6.5× | 0.0% |   0.1538 |
|       OK |   17 |   35.1 | 0.0% | 0.336 | 0.0 |       15 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   24 |  128.9 | 0.0% | 0.312 | 0.0 |       24 |    - |   0.0% |    - | 0.0% |   0.0833 |
|      ALL |   69 |   58.5 | 1.5% | 0.375 | 0.0 |       65 | 100.0% |  16.7% | 10.8× | 0.0% |   0.0923 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   28 |   12.4 | 3.6% | 0.259 | 0.0 |       26 | 0.0% |   0.0% |    - | 4.2% |   0.0769 |
|       OK |   17 |   35.1 | 5.9% | 0.273 | 0.1 |       15 | 0.0% |      - |    - | 6.7% |   0.0000 |
| DEGRADED |   24 |  128.9 | 4.2% | 0.217 | 0.0 |       24 | 0.0% |   0.0% |    - | 4.3% |   0.0417 |
|      ALL |   69 |   58.5 | 4.3% | 0.248 | 0.0 |       65 | 0.0% |   0.0% |    - | 4.8% |   0.0462 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   10.8 | 25.0% | 0.565 | 0.2 |       10 | 100.0% |  50.0% | 1.7× | 0.0% |   0.6000 |
|       OK |    6 |   34.2 | 0.0% | 0.313 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   12 |  153.7 | 0.0% | 0.371 | 0.0 |       12 |    - |   0.0% |    - | 0.0% |   0.3333 |
|      ALL |   30 |   72.6 | 10.0% | 0.437 | 0.1 |       26 | 100.0% |  30.0% | 2.6× | 0.0% |   0.3846 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   10.8 | 8.3% | 0.555 | 0.1 |       10 | 100.0% |  50.0% | 5.0× | 0.0% |   0.2000 |
|       OK |    6 |   34.2 | 0.0% | 0.242 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   12 |  153.7 | 0.0% | 0.314 | 0.0 |       12 |    - |   0.0% |    - | 0.0% |   0.1667 |
|      ALL |   30 |   72.6 | 3.3% | 0.396 | 0.0 |       26 | 100.0% |  25.0% | 6.5× | 0.0% |   0.1538 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   10.8 | 0.0% | 0.295 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.1000 |
|       OK |    6 |   34.2 | 0.0% | 0.118 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   12 |  153.7 | 0.0% | 0.170 | 0.0 |       12 |    - |   0.0% |    - | 0.0% |   0.0833 |
|      ALL |   30 |   72.6 | 0.0% | 0.210 | 0.0 |       26 |    - |   0.0% |    - | 0.0% |   0.0769 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available