# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-08-21 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (81.8%) is 81.8% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (10.6%) is 2.4× the overall rate (4.3%) — score distribution shift detected
🟢 **X+**: FRESH precision (16.7%) is 16.7% HIGHER than DEGRADED (0.0%) — fresher data is helping

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   66 |   12.5 | 19.7% | 0.514 | 0.2 |       63 | 81.8% |  31.0% | 1.8× | 5.9% |   0.4603 |
|       OK |   34 |   37.0 | 8.8% | 0.411 | 0.1 |       33 | 50.0% |  25.0% | 4.1× | 3.5% |   0.1212 |
| DEGRADED |   61 |  118.1 | 8.2% | 0.406 | 0.1 |       61 | 0.0% |   0.0% |    - | 10.6% |   0.2295 |
|      ALL |  161 |   57.7 | 13.0% | 0.452 | 0.1 |      157 | 55.6% |  21.3% | 1.9× | 7.3% |   0.2994 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   66 |   12.5 | 10.6% | 0.504 | 0.1 |       63 | 57.1% |  36.4% | 3.3× | 5.8% |   0.1746 |
|       OK |   34 |   37.0 | 0.0% | 0.344 | 0.0 |       33 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   61 |  118.1 | 0.0% | 0.337 | 0.0 |       61 |    - |   0.0% |    - | 0.0% |   0.0492 |
|      ALL |  161 |   57.7 | 4.3% | 0.407 | 0.0 |      157 | 57.1% |  28.6% | 6.4× | 2.1% |   0.0892 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   66 |   12.5 | 9.1% | 0.368 | 0.1 |       63 | 16.7% |  20.0% | 2.1× | 8.6% |   0.0794 |
|       OK |   34 |   37.0 | 5.9% | 0.315 | 0.1 |       33 | 0.0% |      - |    - | 6.1% |   0.0000 |
| DEGRADED |   61 |  118.1 | 4.9% | 0.291 | 0.1 |       61 | 0.0% |   0.0% |    - | 5.0% |   0.0164 |
|      ALL |  161 |   57.7 | 6.8% | 0.328 | 0.1 |      157 | 9.1% |  16.7% | 2.4× | 6.6% |   0.0382 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   15.0 | 33.3% | 0.605 | 0.4 |        6 | 100.0% | 100.0% | 6.0× | 0.0% |   0.1667 |
|       OK |    6 |   35.9 | 33.3% | 0.516 | 0.3 |        5 | 0.0% |      - |    - | 20.0% |   0.0000 |
| DEGRADED |   13 |  129.1 | 0.0% | 0.389 | 0.0 |       13 |    - |   0.0% |    - | 0.0% |   0.1538 |
|      ALL |   28 |   72.4 | 17.9% | 0.486 | 0.2 |       24 | 50.0% |  33.3% | 4.0× | 4.8% |   0.1250 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   15.0 | 11.1% | 0.638 | 0.1 |        6 | 0.0% |      - |    - | 16.7% |   0.0000 |
|       OK |    6 |   35.9 | 0.0% | 0.452 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |  129.1 | 0.0% | 0.346 | 0.0 |       13 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   28 |   72.4 | 3.6% | 0.463 | 0.0 |       24 | 0.0% |      - |    - | 4.2% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   15.0 | 0.0% | 0.515 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    6 |   35.9 | 0.0% | 0.359 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |  129.1 | 0.0% | 0.248 | 0.0 |       13 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   28 |   72.4 | 0.0% | 0.358 | 0.0 |       24 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available