# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-05-12 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (100.0%) is 100.0% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (3.9%) is 2.4× the overall rate (1.6%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   26 |   12.6 | 11.5% | 0.478 | 0.1 |       25 | 100.0% |  21.4% | 1.8× | 0.0% |   0.5600 |
|       OK |   15 |   35.8 | 6.7% | 0.419 | 0.1 |       13 | 100.0% |  33.3% | 4.3× | 0.0% |   0.2308 |
| DEGRADED |   22 |  133.7 | 9.1% | 0.368 | 0.1 |       21 | 0.0% |   0.0% |    - | 11.8% |   0.1905 |
|      ALL |   63 |   60.4 | 9.5% | 0.425 | 0.1 |       59 | 66.7% |  19.1% | 1.9× | 5.3% |   0.3559 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   26 |   12.6 | 3.9% | 0.465 | 0.0 |       25 | 100.0% |  25.0% | 6.2× | 0.0% |   0.1600 |
|       OK |   15 |   35.8 | 0.0% | 0.364 | 0.0 |       13 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   22 |  133.7 | 0.0% | 0.313 | 0.0 |       21 |    - |   0.0% |    - | 0.0% |   0.0476 |
|      ALL |   63 |   60.4 | 1.6% | 0.388 | 0.0 |       59 | 100.0% |  20.0% | 11.8× | 0.0% |   0.0847 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   26 |   12.6 | 3.9% | 0.255 | 0.0 |       25 | 0.0% |   0.0% |    - | 4.3% |   0.0800 |
|       OK |   15 |   35.8 | 6.7% | 0.304 | 0.1 |       13 | 0.0% |      - |    - | 7.7% |   0.0000 |
| DEGRADED |   22 |  133.7 | 4.5% | 0.220 | 0.1 |       21 | 0.0% |   0.0% |    - | 5.0% |   0.0476 |
|      ALL |   63 |   60.4 | 4.8% | 0.255 | 0.1 |       59 | 0.0% |   0.0% |    - | 5.4% |   0.0508 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   11.0 | 30.0% | 0.601 | 0.3 |        9 | 100.0% |  50.0% | 1.5× | 0.0% |   0.6667 |
|       OK |    4 |   36.4 | 0.0% | 0.366 | 0.0 |        2 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   16 |  154.1 | 0.0% | 0.365 | 0.0 |       15 |    - |   0.0% |    - | 0.0% |   0.2000 |
|      ALL |   30 |   90.7 | 10.0% | 0.444 | 0.1 |       26 | 100.0% |  33.3% | 2.9× | 0.0% |   0.3462 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   11.0 | 10.0% | 0.609 | 0.1 |        9 | 100.0% |  50.0% | 4.5× | 0.0% |   0.2222 |
|       OK |    4 |   36.4 | 0.0% | 0.300 | 0.0 |        2 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   16 |  154.1 | 0.0% | 0.315 | 0.0 |       15 |    - |   0.0% |    - | 0.0% |   0.0667 |
|      ALL |   30 |   90.7 | 3.3% | 0.411 | 0.0 |       26 | 100.0% |  33.3% | 8.7× | 0.0% |   0.1154 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   11.0 | 0.0% | 0.293 | 0.0 |        9 |    - |   0.0% |    - | 0.0% |   0.1111 |
|       OK |    4 |   36.4 | 0.0% | 0.159 | 0.0 |        2 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   16 |  154.1 | 0.0% | 0.173 | 0.0 |       15 |    - |   0.0% |    - | 0.0% |   0.0667 |
|      ALL |   30 |   90.7 | 0.0% | 0.211 | 0.0 |       26 |    - |   0.0% |    - | 0.0% |   0.0769 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available