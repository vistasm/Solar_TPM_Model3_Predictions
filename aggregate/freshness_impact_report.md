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
| DEGRADED |   98 |  117.0 | 12.2% | 0.411 | 0.1 |       98 | 33.3% |  20.0% | 1.6× | 10.3% |   0.2041 |
|      ALL |  218 |   64.1 | 16.1% | 0.446 | 0.2 |      218 | 54.3% |  31.1% | 1.9× | 10.2% |   0.2798 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   79 |   12.7 | 8.9% | 0.492 | 0.1 |       79 | 57.1% |  30.8% | 3.5× | 4.5% |   0.1646 |
|       OK |   41 |   36.8 | 0.0% | 0.347 | 0.0 |       41 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   98 |  117.0 | 4.1% | 0.343 | 0.0 |       98 | 50.0% |  40.0% | 9.8× | 2.1% |   0.0510 |
|      ALL |  218 |   64.1 | 5.1% | 0.398 | 0.1 |      218 | 54.5% |  33.3% | 6.6× | 2.5% |   0.0826 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   79 |   12.7 | 8.9% | 0.373 | 0.1 |       79 | 14.3% |  20.0% | 2.3× | 8.1% |   0.0633 |
|       OK |   41 |   36.8 | 4.9% | 0.316 | 0.1 |       41 | 0.0% |      - |    - | 4.9% |   0.0000 |
| DEGRADED |   98 |  117.0 | 5.1% | 0.282 | 0.1 |       98 | 0.0% |   0.0% |    - | 5.1% |   0.0102 |
|      ALL |  218 |   64.1 | 6.4% | 0.321 | 0.1 |      218 | 7.1% |  16.7% | 2.6× | 6.1% |   0.0275 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |   14 |   97.4 | 35.7% | 0.548 | 0.4 |       14 | 60.0% |  60.0% | 1.7× | 22.2% |   0.3571 |
|      ALL |   14 |   97.4 | 35.7% | 0.548 | 0.4 |       14 | 60.0% |  60.0% | 1.7× | 22.2% |   0.3571 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |   14 |   97.4 | 28.6% | 0.495 | 0.3 |       14 | 50.0% | 100.0% | 3.5× | 16.7% |   0.1429 |
|      ALL |   14 |   97.4 | 28.6% | 0.495 | 0.3 |       14 | 50.0% | 100.0% | 3.5× | 16.7% |   0.1429 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |   14 |   97.4 | 7.1% | 0.385 | 0.1 |       14 | 0.0% |      - |    - | 7.1% |   0.0000 |
|      ALL |   14 |   97.4 | 7.1% | 0.385 | 0.1 |       14 | 0.0% |      - |    - | 7.1% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available