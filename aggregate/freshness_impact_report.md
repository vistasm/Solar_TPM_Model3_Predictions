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

🟢 **M+**: FRESH precision (72.2%) is 47.2% HIGHER than DEGRADED (25.0%) — fresher data is helping
🔴 **M5+**: FRESH precision (57.1%) is 42.9% LOWER than DEGRADED (100.0%) — fresher data may be hurting
🟡 **M5+**: FRESH alert rate (8.9%) is 2.4× the overall rate (3.8%) — score distribution shift detected
🟢 **X+**: FRESH precision (14.3%) is 14.3% HIGHER than DEGRADED (0.0%) — fresher data is helping

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   79 |   12.7 | 22.8% | 0.507 | 0.3 |       79 | 72.2% |  36.1% | 1.6× | 11.6% |   0.4557 |
|       OK |   41 |   36.8 | 12.2% | 0.414 | 0.1 |       41 | 40.0% |  40.0% | 3.3× | 8.3% |   0.1220 |
| DEGRADED |   93 |  118.0 | 8.6% | 0.388 | 0.1 |       93 | 25.0% |  11.1% | 1.3× | 8.0% |   0.1935 |
|      ALL |  213 |   63.3 | 14.5% | 0.437 | 0.2 |      213 | 54.8% |  28.8% | 2.0× | 9.1% |   0.2770 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   79 |   12.7 | 8.9% | 0.492 | 0.1 |       79 | 57.1% |  30.8% | 3.5× | 4.5% |   0.1646 |
|       OK |   41 |   36.8 | 0.0% | 0.347 | 0.0 |       41 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   93 |  118.0 | 1.1% | 0.316 | 0.0 |       93 | 100.0% |  25.0% | 23.2× | 0.0% |   0.0430 |
|      ALL |  213 |   63.3 | 3.8% | 0.387 | 0.0 |      213 | 62.5% |  29.4% | 7.8× | 1.5% |   0.0798 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   79 |   12.7 | 8.9% | 0.373 | 0.1 |       79 | 14.3% |  20.0% | 2.3× | 8.1% |   0.0633 |
|       OK |   41 |   36.8 | 4.9% | 0.316 | 0.1 |       41 | 0.0% |      - |    - | 4.9% |   0.0000 |
| DEGRADED |   93 |  118.0 | 5.4% | 0.265 | 0.1 |       93 | 0.0% |   0.0% |    - | 5.4% |   0.0108 |
|      ALL |  213 |   63.3 | 6.6% | 0.315 | 0.1 |      213 | 7.1% |  16.7% | 2.5× | 6.3% |   0.0282 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |    9 |   97.3 | 11.1% | 0.387 | 0.1 |        9 | 100.0% |  33.3% | 3.0× | 0.0% |   0.3333 |
|      ALL |    9 |   97.3 | 11.1% | 0.387 | 0.1 |        9 | 100.0% |  33.3% | 3.0× | 0.0% |   0.3333 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |    9 |   97.3 | 11.1% | 0.305 | 0.1 |        9 | 100.0% | 100.0% | 9.0× | 0.0% |   0.1111 |
|      ALL |    9 |   97.3 | 11.1% | 0.305 | 0.1 |        9 | 100.0% | 100.0% | 9.0× | 0.0% |   0.1111 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |    9 |   97.3 | 11.1% | 0.260 | 0.1 |        9 | 0.0% |      - |    - | 11.1% |   0.0000 |
|      ALL |    9 |   97.3 | 11.1% | 0.260 | 0.1 |        9 | 0.0% |      - |    - | 11.1% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available