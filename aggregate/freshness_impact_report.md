# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-10-30 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (72.2%) is 38.9% HIGHER than DEGRADED (33.3%) — fresher data is helping
🟢 **M5+**: FRESH precision (57.1%) is 7.1% HIGHER than DEGRADED (50.0%) — fresher data is helping
🟢 **X+**: FRESH precision (14.3%) is 14.3% HIGHER than DEGRADED (0.0%) — fresher data is helping

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   79 |   12.7 | 22.8% | 0.507 | 0.3 |       79 | 72.2% |  36.1% | 1.6× | 11.6% |   0.4557 |
|       OK |   41 |   36.8 | 12.2% | 0.414 | 0.1 |       41 | 40.0% |  40.0% | 3.3× | 8.3% |   0.1220 |
| DEGRADED |  101 |  116.4 | 11.9% | 0.413 | 0.1 |      101 | 33.3% |  19.1% | 1.6× | 10.0% |   0.2079 |
|      ALL |  221 |   64.6 | 15.8% | 0.447 | 0.2 |      221 | 54.3% |  30.6% | 1.9× | 10.1% |   0.2805 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   79 |   12.7 | 8.9% | 0.492 | 0.1 |       79 | 57.1% |  30.8% | 3.5× | 4.5% |   0.1646 |
|       OK |   41 |   36.8 | 0.0% | 0.347 | 0.0 |       41 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |  101 |  116.4 | 4.0% | 0.349 | 0.0 |      101 | 50.0% |  40.0% | 10.1× | 2.1% |   0.0495 |
|      ALL |  221 |   64.6 | 5.0% | 0.400 | 0.1 |      221 | 54.5% |  33.3% | 6.7× | 2.5% |   0.0814 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   79 |   12.7 | 8.9% | 0.373 | 0.1 |       79 | 14.3% |  20.0% | 2.3× | 8.1% |   0.0633 |
|       OK |   41 |   36.8 | 4.9% | 0.316 | 0.1 |       41 | 0.0% |      - |    - | 4.9% |   0.0000 |
| DEGRADED |  101 |  116.4 | 5.0% | 0.284 | 0.1 |      101 | 0.0% |   0.0% |    - | 5.0% |   0.0099 |
|      ALL |  221 |   64.6 | 6.3% | 0.322 | 0.1 |      221 | 7.1% |  16.7% | 2.6× | 6.0% |   0.0271 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |   17 |   97.4 | 29.4% | 0.532 | 0.3 |       17 | 60.0% |  50.0% | 1.7× | 18.2% |   0.3529 |
|      ALL |   17 |   97.4 | 29.4% | 0.532 | 0.3 |       17 | 60.0% |  50.0% | 1.7× | 18.2% |   0.3529 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |   17 |   97.4 | 23.5% | 0.505 | 0.2 |       17 | 50.0% | 100.0% | 4.2× | 13.3% |   0.1176 |
|      ALL |   17 |   97.4 | 23.5% | 0.505 | 0.2 |       17 | 50.0% | 100.0% | 4.2× | 13.3% |   0.1176 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |   17 |   97.4 | 5.9% | 0.376 | 0.1 |       17 | 0.0% |      - |    - | 5.9% |   0.0000 |
|      ALL |   17 |   97.4 | 5.9% | 0.376 | 0.1 |       17 | 0.0% |      - |    - | 5.9% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available