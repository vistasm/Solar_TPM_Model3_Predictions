# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-09-26 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (72.2%) is 55.5% HIGHER than DEGRADED (16.7%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (8.9%) is 2.5× the overall rate (3.6%) — score distribution shift detected
🟢 **X+**: FRESH precision (14.3%) is 14.3% HIGHER than DEGRADED (0.0%) — fresher data is helping

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   79 |   12.7 | 22.8% | 0.507 | 0.3 |       79 | 72.2% |  36.1% | 1.6× | 11.6% |   0.4557 |
|       OK |   41 |   36.8 | 12.2% | 0.414 | 0.1 |       41 | 40.0% |  40.0% | 3.3× | 8.3% |   0.1220 |
| DEGRADED |   75 |  118.8 | 8.0% | 0.392 | 0.1 |       71 | 16.7% |   6.7% | 0.8× | 8.9% |   0.2113 |
|      ALL |  195 |   58.6 | 14.9% | 0.443 | 0.2 |      191 | 55.2% |  28.6% | 1.9× | 9.6% |   0.2932 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   79 |   12.7 | 8.9% | 0.492 | 0.1 |       79 | 57.1% |  30.8% | 3.5× | 4.5% |   0.1646 |
|       OK |   41 |   36.8 | 0.0% | 0.347 | 0.0 |       41 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   75 |  118.8 | 0.0% | 0.321 | 0.0 |       71 |    - |   0.0% |    - | 0.0% |   0.0423 |
|      ALL |  195 |   58.6 | 3.6% | 0.396 | 0.0 |      191 | 57.1% |  25.0% | 6.8× | 1.7% |   0.0838 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   79 |   12.7 | 8.9% | 0.373 | 0.1 |       79 | 14.3% |  20.0% | 2.3× | 8.1% |   0.0633 |
|       OK |   41 |   36.8 | 4.9% | 0.316 | 0.1 |       41 | 0.0% |      - |    - | 4.9% |   0.0000 |
| DEGRADED |   75 |  118.8 | 4.0% | 0.264 | 0.0 |       71 | 0.0% |   0.0% |    - | 4.3% |   0.0141 |
|      ALL |  195 |   58.6 | 6.2% | 0.319 | 0.1 |      191 | 8.3% |  16.7% | 2.6× | 5.9% |   0.0314 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   13.5 | 20.0% | 0.372 | 0.2 |       10 | 50.0% |  33.3% | 1.7× | 14.3% |   0.3000 |
|       OK |    6 |   34.7 | 16.7% | 0.388 | 0.2 |        6 | 0.0% |      - |    - | 16.7% |   0.0000 |
| DEGRADED |   13 |  125.7 | 0.0% | 0.303 | 0.0 |        9 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   29 |   68.2 | 10.3% | 0.344 | 0.1 |       25 | 33.3% |  33.3% | 2.8× | 9.1% |   0.1200 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   13.5 | 0.0% | 0.318 | 0.0 |       10 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    6 |   34.7 | 0.0% | 0.320 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |  125.7 | 0.0% | 0.223 | 0.0 |        9 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   29 |   68.2 | 0.0% | 0.276 | 0.0 |       25 |    - |      - |    - | 0.0% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   13.5 | 10.0% | 0.352 | 0.1 |       10 | 0.0% |      - |    - | 10.0% |   0.0000 |
|       OK |    6 |   34.7 | 0.0% | 0.291 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |  125.7 | 0.0% | 0.124 | 0.0 |        9 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   29 |   68.2 | 3.5% | 0.237 | 0.0 |       25 | 0.0% |      - |    - | 4.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available