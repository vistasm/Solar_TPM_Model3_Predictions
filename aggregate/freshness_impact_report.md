# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-05-15 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (100.0%) is 100.0% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (3.9%) is 2.5× the overall rate (1.5%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   26 |   12.6 | 11.5% | 0.478 | 0.1 |       26 | 100.0% |  21.4% | 1.9× | 0.0% |   0.5385 |
|       OK |   16 |   35.7 | 6.2% | 0.406 | 0.1 |       14 | 100.0% |  33.3% | 4.7× | 0.0% |   0.2143 |
| DEGRADED |   24 |  128.9 | 8.3% | 0.371 | 0.1 |       22 | 0.0% |   0.0% |    - | 11.8% |   0.2273 |
|      ALL |   66 |   60.5 | 9.1% | 0.422 | 0.1 |       62 | 66.7% |  18.2% | 1.9× | 5.0% |   0.3548 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   26 |   12.6 | 3.9% | 0.465 | 0.0 |       26 | 100.0% |  25.0% | 6.5× | 0.0% |   0.1538 |
|       OK |   16 |   35.7 | 0.0% | 0.352 | 0.0 |       14 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   24 |  128.9 | 0.0% | 0.312 | 0.0 |       22 |    - |   0.0% |    - | 0.0% |   0.0909 |
|      ALL |   66 |   60.5 | 1.5% | 0.382 | 0.0 |       62 | 100.0% |  16.7% | 10.3× | 0.0% |   0.0968 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   26 |   12.6 | 3.9% | 0.255 | 0.0 |       26 | 0.0% |   0.0% |    - | 4.2% |   0.0769 |
|       OK |   16 |   35.7 | 6.2% | 0.287 | 0.1 |       14 | 0.0% |      - |    - | 7.1% |   0.0000 |
| DEGRADED |   24 |  128.9 | 4.2% | 0.217 | 0.0 |       22 | 0.0% |   0.0% |    - | 4.8% |   0.0455 |
|      ALL |   66 |   60.5 | 4.5% | 0.249 | 0.1 |       62 | 0.0% |   0.0% |    - | 5.1% |   0.0484 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   11.0 | 30.0% | 0.601 | 0.3 |       10 | 100.0% |  50.0% | 1.7× | 0.0% |   0.6000 |
|       OK |    5 |   35.8 | 0.0% | 0.335 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   15 |  155.9 | 0.0% | 0.366 | 0.0 |       13 |    - |   0.0% |    - | 0.0% |   0.3077 |
|      ALL |   30 |   87.6 | 10.0% | 0.439 | 0.1 |       26 | 100.0% |  30.0% | 2.6× | 0.0% |   0.3846 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   11.0 | 10.0% | 0.609 | 0.1 |       10 | 100.0% |  50.0% | 5.0× | 0.0% |   0.2000 |
|       OK |    5 |   35.8 | 0.0% | 0.275 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   15 |  155.9 | 0.0% | 0.309 | 0.0 |       13 |    - |   0.0% |    - | 0.0% |   0.1538 |
|      ALL |   30 |   87.6 | 3.3% | 0.404 | 0.0 |       26 | 100.0% |  25.0% | 6.5× | 0.0% |   0.1538 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   11.0 | 0.0% | 0.293 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.1000 |
|       OK |    5 |   35.8 | 0.0% | 0.134 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   15 |  155.9 | 0.0% | 0.152 | 0.0 |       13 |    - |   0.0% |    - | 0.0% |   0.0769 |
|      ALL |   30 |   87.6 | 0.0% | 0.196 | 0.0 |       26 |    - |   0.0% |    - | 0.0% |   0.0769 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available