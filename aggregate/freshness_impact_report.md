# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-05-19 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (100.0%) is 100.0% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (3.6%) is 2.5× the overall rate (1.4%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   28 |   12.4 | 10.7% | 0.471 | 0.1 |       26 | 100.0% |  21.4% | 1.9× | 0.0% |   0.5385 |
|       OK |   17 |   35.1 | 5.9% | 0.394 | 0.1 |       16 | 100.0% |  33.3% | 5.3× | 0.0% |   0.1875 |
| DEGRADED |   25 |  125.7 | 8.0% | 0.368 | 0.1 |       24 | 0.0% |   0.0% |    - | 10.5% |   0.2083 |
|      ALL |   70 |   58.4 | 8.6% | 0.415 | 0.1 |       66 | 66.7% |  18.2% | 2.0× | 4.5% |   0.3333 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   28 |   12.4 | 3.6% | 0.452 | 0.0 |       26 | 100.0% |  25.0% | 6.5× | 0.0% |   0.1538 |
|       OK |   17 |   35.1 | 0.0% | 0.336 | 0.0 |       16 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   25 |  125.7 | 0.0% | 0.304 | 0.0 |       24 |    - |   0.0% |    - | 0.0% |   0.0833 |
|      ALL |   70 |   58.4 | 1.4% | 0.371 | 0.0 |       66 | 100.0% |  16.7% | 11.0× | 0.0% |   0.0909 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   28 |   12.4 | 3.6% | 0.259 | 0.0 |       26 | 0.0% |   0.0% |    - | 4.2% |   0.0769 |
|       OK |   17 |   35.1 | 5.9% | 0.273 | 0.1 |       16 | 0.0% |      - |    - | 6.2% |   0.0000 |
| DEGRADED |   25 |  125.7 | 4.0% | 0.212 | 0.0 |       24 | 0.0% |   0.0% |    - | 4.3% |   0.0417 |
|      ALL |   70 |   58.4 | 4.3% | 0.245 | 0.0 |       66 | 0.0% |   0.0% |    - | 4.8% |   0.0455 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   10.8 | 25.0% | 0.565 | 0.2 |       10 | 100.0% |  50.0% | 1.7× | 0.0% |   0.6000 |
|       OK |    6 |   34.2 | 0.0% | 0.313 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   12 |  140.1 | 0.0% | 0.359 | 0.0 |       11 |    - |   0.0% |    - | 0.0% |   0.3636 |
|      ALL |   30 |   67.2 | 10.0% | 0.432 | 0.1 |       26 | 100.0% |  30.0% | 2.6× | 0.0% |   0.3846 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   10.8 | 8.3% | 0.555 | 0.1 |       10 | 100.0% |  50.0% | 5.0× | 0.0% |   0.2000 |
|       OK |    6 |   34.2 | 0.0% | 0.242 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   12 |  140.1 | 0.0% | 0.289 | 0.0 |       11 |    - |   0.0% |    - | 0.0% |   0.1818 |
|      ALL |   30 |   67.2 | 3.3% | 0.386 | 0.0 |       26 | 100.0% |  25.0% | 6.5× | 0.0% |   0.1538 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   10.8 | 0.0% | 0.295 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.1000 |
|       OK |    6 |   34.2 | 0.0% | 0.118 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   12 |  140.1 | 0.0% | 0.167 | 0.0 |       11 |    - |   0.0% |    - | 0.0% |   0.0909 |
|      ALL |   30 |   67.2 | 0.0% | 0.209 | 0.0 |       26 |    - |   0.0% |    - | 0.0% |   0.0769 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available