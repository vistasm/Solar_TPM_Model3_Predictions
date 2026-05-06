# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-05-06 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (100.0%) is 100.0% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (4.2%) is 2.4× the overall rate (1.8%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   24 |   12.4 | 12.5% | 0.486 | 0.1 |       22 | 100.0% |  23.1% | 1.7× | 0.0% |   0.5909 |
|       OK |   13 |   35.4 | 7.7% | 0.429 | 0.1 |       12 | 100.0% |  33.3% | 4.0× | 0.0% |   0.2500 |
| DEGRADED |   20 |  140.2 | 10.0% | 0.375 | 0.1 |       19 | 0.0% |   0.0% |    - | 12.5% |   0.1579 |
|      ALL |   57 |   62.5 | 10.5% | 0.434 | 0.1 |       53 | 66.7% |  21.1% | 1.9× | 5.9% |   0.3585 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   24 |   12.4 | 4.2% | 0.472 | 0.0 |       22 | 100.0% |  25.0% | 5.5× | 0.0% |   0.1818 |
|       OK |   13 |   35.4 | 0.0% | 0.372 | 0.0 |       12 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   20 |  140.2 | 0.0% | 0.317 | 0.0 |       19 |    - |   0.0% |    - | 0.0% |   0.0526 |
|      ALL |   57 |   62.5 | 1.8% | 0.395 | 0.0 |       53 | 100.0% |  20.0% | 10.6× | 0.0% |   0.0943 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   24 |   12.4 | 4.2% | 0.262 | 0.0 |       22 | 0.0% |   0.0% |    - | 5.0% |   0.0909 |
|       OK |   13 |   35.4 | 7.7% | 0.335 | 0.1 |       12 | 0.0% |      - |    - | 8.3% |   0.0000 |
| DEGRADED |   20 |  140.2 | 5.0% | 0.222 | 0.1 |       19 | 0.0% |   0.0% |    - | 5.6% |   0.0526 |
|      ALL |   57 |   62.5 | 5.3% | 0.264 | 0.1 |       53 | 0.0% |   0.0% |    - | 6.0% |   0.0566 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   11.2 | 33.3% | 0.612 | 0.3 |        7 | 100.0% |  60.0% | 1.4× | 0.0% |   0.7143 |
|       OK |    5 |   34.5 | 20.0% | 0.449 | 0.2 |        4 | 100.0% | 100.0% | 4.0× | 0.0% |   0.2500 |
| DEGRADED |   16 |  153.7 | 0.0% | 0.362 | 0.0 |       15 |    - |   0.0% |    - | 0.0% |   0.1333 |
|      ALL |   30 |   91.1 | 13.3% | 0.452 | 0.1 |       26 | 100.0% |  50.0% | 3.2× | 0.0% |   0.3077 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   11.2 | 11.1% | 0.604 | 0.1 |        7 | 100.0% |  50.0% | 3.5× | 0.0% |   0.2857 |
|       OK |    5 |   34.5 | 0.0% | 0.361 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   16 |  153.7 | 0.0% | 0.312 | 0.0 |       15 |    - |   0.0% |    - | 0.0% |   0.0667 |
|      ALL |   30 |   91.1 | 3.3% | 0.408 | 0.0 |       26 | 100.0% |  33.3% | 8.7× | 0.0% |   0.1154 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   11.2 | 0.0% | 0.291 | 0.0 |        7 |    - |   0.0% |    - | 0.0% |   0.1429 |
|       OK |    5 |   34.5 | 20.0% | 0.316 | 0.2 |        4 | 0.0% |      - |    - | 25.0% |   0.0000 |
| DEGRADED |   16 |  153.7 | 0.0% | 0.160 | 0.0 |       15 |    - |   0.0% |    - | 0.0% |   0.0667 |
|      ALL |   30 |   91.1 | 3.3% | 0.225 | 0.0 |       26 | 0.0% |   0.0% |    - | 4.2% |   0.0769 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available