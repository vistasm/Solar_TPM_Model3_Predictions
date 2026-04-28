# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-04-28 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (100.0%) is 100.0% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (4.8%) is 2.3× the overall rate (2.0%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   21 |   12.7 | 14.3% | 0.477 | 0.1 |       17 | 100.0% |  11.1% | 1.9× | 0.0% |   0.5294 |
|       OK |   11 |   35.7 | 9.1% | 0.438 | 0.1 |       11 | 100.0% |  33.3% | 3.7× | 0.0% |   0.2727 |
| DEGRADED |   17 |  153.0 | 11.8% | 0.373 | 0.1 |       17 | 0.0% |   0.0% |    - | 14.3% |   0.1765 |
|      ALL |   49 |   66.5 | 12.2% | 0.432 | 0.1 |       45 | 50.0% |  13.3% | 1.5× | 6.7% |   0.3333 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   21 |   12.7 | 4.8% | 0.471 | 0.1 |       17 |    - |   0.0% |    - | 0.0% |   0.1765 |
|       OK |   11 |   35.7 | 0.0% | 0.387 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   17 |  153.0 | 0.0% | 0.325 | 0.0 |       17 |    - |   0.0% |    - | 0.0% |   0.0588 |
|      ALL |   49 |   66.5 | 2.0% | 0.402 | 0.0 |       45 |    - |   0.0% |    - | 0.0% |   0.0889 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   21 |   12.7 | 4.8% | 0.264 | 0.1 |       17 | 0.0% |   0.0% |    - | 6.7% |   0.1176 |
|       OK |   11 |   35.7 | 9.1% | 0.357 | 0.1 |       11 | 0.0% |      - |    - | 9.1% |   0.0000 |
| DEGRADED |   17 |  153.0 | 5.9% | 0.245 | 0.1 |       17 | 0.0% |   0.0% |    - | 6.2% |   0.0588 |
|      ALL |   49 |   66.5 | 6.1% | 0.278 | 0.1 |       45 | 0.0% |   0.0% |    - | 7.1% |   0.0667 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   10.6 | 23.1% | 0.494 | 0.2 |        9 | 100.0% |  20.0% | 1.8× | 0.0% |   0.5556 |
|       OK |    4 |   32.9 | 25.0% | 0.455 | 0.2 |        4 | 100.0% | 100.0% | 4.0× | 0.0% |   0.2500 |
| DEGRADED |   13 |  173.6 | 0.0% | 0.357 | 0.0 |       13 |    - |   0.0% |    - | 0.0% |   0.1538 |
|      ALL |   30 |   84.2 | 13.3% | 0.429 | 0.1 |       26 | 100.0% |  25.0% | 3.2× | 0.0% |   0.3077 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   10.6 | 7.7% | 0.513 | 0.1 |        9 |    - |   0.0% |    - | 0.0% |   0.3333 |
|       OK |    4 |   32.9 | 0.0% | 0.399 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |  173.6 | 0.0% | 0.322 | 0.0 |       13 |    - |   0.0% |    - | 0.0% |   0.0769 |
|      ALL |   30 |   84.2 | 3.3% | 0.415 | 0.0 |       26 |    - |   0.0% |    - | 0.0% |   0.1538 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   10.6 | 7.7% | 0.266 | 0.1 |        9 | 0.0% |   0.0% |    - | 14.3% |   0.2222 |
|       OK |    4 |   32.9 | 25.0% | 0.317 | 0.2 |        4 | 0.0% |      - |    - | 25.0% |   0.0000 |
| DEGRADED |   13 |  173.6 | 0.0% | 0.177 | 0.0 |       13 |    - |   0.0% |    - | 0.0% |   0.0769 |
|      ALL |   30 |   84.2 | 6.7% | 0.234 | 0.1 |       26 | 0.0% |   0.0% |    - | 8.7% |   0.1154 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available