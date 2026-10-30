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

🟢 **M+**: FRESH precision (72.2%) is 57.9% HIGHER than DEGRADED (14.3%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (8.9%) is 2.6× the overall rate (3.4%) — score distribution shift detected
🟢 **X+**: FRESH precision (14.3%) is 14.3% HIGHER than DEGRADED (0.0%) — fresher data is helping

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   79 |   12.7 | 22.8% | 0.507 | 0.3 |       79 | 72.2% |  36.1% | 1.6× | 11.6% |   0.4557 |
|       OK |   41 |   36.8 | 12.2% | 0.414 | 0.1 |       41 | 40.0% |  40.0% | 3.3× | 8.3% |   0.1220 |
| DEGRADED |   86 |  119.7 | 8.1% | 0.384 | 0.1 |       86 | 14.3% |   6.7% | 0.8× | 8.5% |   0.1744 |
|      ALL |  206 |   62.2 | 14.6% | 0.437 | 0.2 |      206 | 53.3% |  28.6% | 2.0× | 9.3% |   0.2718 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   79 |   12.7 | 8.9% | 0.492 | 0.1 |       79 | 57.1% |  30.8% | 3.5× | 4.5% |   0.1646 |
|       OK |   41 |   36.8 | 0.0% | 0.347 | 0.0 |       41 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   86 |  119.7 | 0.0% | 0.312 | 0.0 |       86 |    - |   0.0% |    - | 0.0% |   0.0349 |
|      ALL |  206 |   62.2 | 3.4% | 0.388 | 0.0 |      206 | 57.1% |  25.0% | 7.4× | 1.6% |   0.0777 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   79 |   12.7 | 8.9% | 0.373 | 0.1 |       79 | 14.3% |  20.0% | 2.3× | 8.1% |   0.0633 |
|       OK |   41 |   36.8 | 4.9% | 0.316 | 0.1 |       41 | 0.0% |      - |    - | 4.9% |   0.0000 |
| DEGRADED |   86 |  119.7 | 4.7% | 0.261 | 0.1 |       86 | 0.0% |   0.0% |    - | 4.7% |   0.0116 |
|      ALL |  206 |   62.2 | 6.3% | 0.315 | 0.1 |      206 | 7.7% |  16.7% | 2.6× | 6.0% |   0.0291 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |    2 |   97.3 | 0.0% | 0.190 | 0.0 |        2 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |    2 |   97.3 | 0.0% | 0.190 | 0.0 |        2 |    - |      - |    - | 0.0% |   0.0000 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |    2 |   97.3 | 0.0% | 0.101 | 0.0 |        2 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |    2 |   97.3 | 0.0% | 0.101 | 0.0 |        2 |    - |      - |    - | 0.0% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |    2 |   97.3 | 0.0% | 0.099 | 0.0 |        2 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |    2 |   97.3 | 0.0% | 0.099 | 0.0 |        2 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available