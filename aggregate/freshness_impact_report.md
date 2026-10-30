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

🟢 **M+**: FRESH precision (72.2%) is 35.9% HIGHER than DEGRADED (36.4%) — fresher data is helping
🟢 **X+**: FRESH precision (14.3%) is 14.3% HIGHER than DEGRADED (0.0%) — fresher data is helping

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   79 |   12.7 | 22.8% | 0.507 | 0.3 |       79 | 72.2% |  36.1% | 1.6× | 11.6% |   0.4557 |
|       OK |   41 |   36.8 | 12.2% | 0.414 | 0.1 |       41 | 40.0% |  40.0% | 3.3× | 8.3% |   0.1220 |
| DEGRADED |   96 |  117.4 | 11.5% | 0.404 | 0.1 |       96 | 36.4% |  20.0% | 1.8× | 9.2% |   0.2083 |
|      ALL |  216 |   63.8 | 15.7% | 0.443 | 0.2 |      216 | 55.9% |  31.1% | 2.0× | 9.7% |   0.2824 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   79 |   12.7 | 8.9% | 0.492 | 0.1 |       79 | 57.1% |  30.8% | 3.5× | 4.5% |   0.1646 |
|       OK |   41 |   36.8 | 0.0% | 0.347 | 0.0 |       41 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   96 |  117.4 | 3.1% | 0.335 | 0.0 |       96 | 66.7% |  40.0% | 12.8× | 1.1% |   0.0521 |
|      ALL |  216 |   63.8 | 4.6% | 0.395 | 0.1 |      216 | 60.0% |  33.3% | 7.2× | 2.0% |   0.0833 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   79 |   12.7 | 8.9% | 0.373 | 0.1 |       79 | 14.3% |  20.0% | 2.3× | 8.1% |   0.0633 |
|       OK |   41 |   36.8 | 4.9% | 0.316 | 0.1 |       41 | 0.0% |      - |    - | 4.9% |   0.0000 |
| DEGRADED |   96 |  117.4 | 5.2% | 0.277 | 0.1 |       96 | 0.0% |   0.0% |    - | 5.3% |   0.0104 |
|      ALL |  216 |   63.8 | 6.5% | 0.319 | 0.1 |      216 | 7.1% |  16.7% | 2.6× | 6.2% |   0.0278 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |   12 |   97.3 | 33.3% | 0.508 | 0.3 |       12 | 75.0% |  60.0% | 1.8× | 14.3% |   0.4167 |
|      ALL |   12 |   97.3 | 33.3% | 0.508 | 0.3 |       12 | 75.0% |  60.0% | 1.8× | 14.3% |   0.4167 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |   12 |   97.3 | 25.0% | 0.455 | 0.2 |       12 | 66.7% | 100.0% | 4.0× | 10.0% |   0.1667 |
|      ALL |   12 |   97.3 | 25.0% | 0.455 | 0.2 |       12 | 66.7% | 100.0% | 4.0× | 10.0% |   0.1667 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |   12 |   97.3 | 8.3% | 0.360 | 0.1 |       12 | 0.0% |      - |    - | 8.3% |   0.0000 |
|      ALL |   12 |   97.3 | 8.3% | 0.360 | 0.1 |       12 | 0.0% |      - |    - | 8.3% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available