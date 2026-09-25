# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-09-25 UTC
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
| DEGRADED |   74 |  118.3 | 8.1% | 0.393 | 0.1 |       70 | 16.7% |   6.7% | 0.8× | 9.1% |   0.2143 |
|      ALL |  194 |   58.1 | 14.9% | 0.444 | 0.2 |      190 | 55.2% |  28.6% | 1.9× | 9.7% |   0.2947 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   79 |   12.7 | 8.9% | 0.492 | 0.1 |       79 | 57.1% |  30.8% | 3.5× | 4.5% |   0.1646 |
|       OK |   41 |   36.8 | 0.0% | 0.347 | 0.0 |       41 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   74 |  118.3 | 0.0% | 0.322 | 0.0 |       70 |    - |   0.0% |    - | 0.0% |   0.0429 |
|      ALL |  194 |   58.1 | 3.6% | 0.397 | 0.0 |      190 | 57.1% |  25.0% | 6.8× | 1.7% |   0.0842 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   79 |   12.7 | 8.9% | 0.373 | 0.1 |       79 | 14.3% |  20.0% | 2.3× | 8.1% |   0.0633 |
|       OK |   41 |   36.8 | 4.9% | 0.316 | 0.1 |       41 | 0.0% |      - |    - | 4.9% |   0.0000 |
| DEGRADED |   74 |  118.3 | 4.0% | 0.265 | 0.0 |       70 | 0.0% |   0.0% |    - | 4.3% |   0.0143 |
|      ALL |  194 |   58.1 | 6.2% | 0.320 | 0.1 |      190 | 8.3% |  16.7% | 2.6× | 6.0% |   0.0316 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   13.8 | 27.3% | 0.413 | 0.3 |       11 | 66.7% |  50.0% | 1.8× | 14.3% |   0.3636 |
|       OK |    6 |   34.7 | 16.7% | 0.388 | 0.2 |        6 | 0.0% |      - |    - | 16.7% |   0.0000 |
| DEGRADED |   12 |  123.2 | 0.0% | 0.305 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   29 |   63.4 | 13.8% | 0.363 | 0.1 |       25 | 50.0% |  50.0% | 3.1× | 9.5% |   0.1600 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   13.8 | 0.0% | 0.368 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    6 |   34.7 | 0.0% | 0.320 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   12 |  123.2 | 0.0% | 0.221 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   29 |   63.4 | 0.0% | 0.297 | 0.0 |       25 |    - |      - |    - | 0.0% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   13.8 | 9.1% | 0.368 | 0.1 |       11 | 0.0% |      - |    - | 9.1% |   0.0000 |
|       OK |    6 |   34.7 | 0.0% | 0.291 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   12 |  123.2 | 0.0% | 0.123 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   29 |   63.4 | 3.5% | 0.251 | 0.0 |       25 | 0.0% |      - |    - | 4.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available