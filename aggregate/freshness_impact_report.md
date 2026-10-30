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
| DEGRADED |  110 |  114.9 | 10.9% | 0.412 | 0.1 |      110 | 33.3% |  18.2% | 1.7× | 9.1% |   0.2000 |
|      ALL |  230 |   65.9 | 15.2% | 0.445 | 0.2 |      230 | 54.3% |  30.2% | 2.0× | 9.6% |   0.2739 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   79 |   12.7 | 8.9% | 0.492 | 0.1 |       79 | 57.1% |  30.8% | 3.5× | 4.5% |   0.1646 |
|       OK |   41 |   36.8 | 0.0% | 0.347 | 0.0 |       41 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |  110 |  114.9 | 3.6% | 0.358 | 0.0 |      110 | 50.0% |  40.0% | 11.0× | 1.9% |   0.0455 |
|      ALL |  230 |   65.9 | 4.8% | 0.402 | 0.1 |      230 | 54.5% |  33.3% | 7.0× | 2.4% |   0.0783 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   79 |   12.7 | 8.9% | 0.373 | 0.1 |       79 | 14.3% |  20.0% | 2.3× | 8.1% |   0.0633 |
|       OK |   41 |   36.8 | 4.9% | 0.316 | 0.1 |       41 | 0.0% |      - |    - | 4.9% |   0.0000 |
| DEGRADED |  110 |  114.9 | 4.5% | 0.283 | 0.1 |      110 | 0.0% |   0.0% |    - | 4.6% |   0.0091 |
|      ALL |  230 |   65.9 | 6.1% | 0.320 | 0.1 |      230 | 7.1% |  16.7% | 2.7× | 5.8% |   0.0261 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |   26 |   97.4 | 19.2% | 0.489 | 0.2 |       26 | 60.0% |  42.9% | 2.2× | 10.5% |   0.2692 |
|      ALL |   26 |   97.4 | 19.2% | 0.489 | 0.2 |       26 | 60.0% |  42.9% | 2.2× | 10.5% |   0.2692 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |   26 |   97.4 | 15.4% | 0.490 | 0.1 |       26 | 50.0% | 100.0% | 6.5× | 8.3% |   0.0769 |
|      ALL |   26 |   97.4 | 15.4% | 0.490 | 0.1 |       26 | 50.0% | 100.0% | 6.5× | 8.3% |   0.0769 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |   26 |   97.4 | 3.9% | 0.341 | 0.0 |       26 | 0.0% |      - |    - | 3.9% |   0.0000 |
|      ALL |   26 |   97.4 | 3.9% | 0.341 | 0.0 |       26 | 0.0% |      - |    - | 3.9% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available