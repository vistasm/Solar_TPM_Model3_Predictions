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
| DEGRADED |  106 |  115.5 | 11.3% | 0.416 | 0.1 |      106 | 33.3% |  18.2% | 1.6× | 9.5% |   0.2075 |
|      ALL |  226 |   65.3 | 15.5% | 0.447 | 0.2 |      226 | 54.3% |  30.2% | 1.9× | 9.8% |   0.2788 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   79 |   12.7 | 8.9% | 0.492 | 0.1 |       79 | 57.1% |  30.8% | 3.5× | 4.5% |   0.1646 |
|       OK |   41 |   36.8 | 0.0% | 0.347 | 0.0 |       41 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |  106 |  115.5 | 3.8% | 0.361 | 0.0 |      106 | 50.0% |  40.0% | 10.6× | 2.0% |   0.0472 |
|      ALL |  226 |   65.3 | 4.9% | 0.405 | 0.1 |      226 | 54.5% |  33.3% | 6.8× | 2.4% |   0.0796 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   79 |   12.7 | 8.9% | 0.373 | 0.1 |       79 | 14.3% |  20.0% | 2.3× | 8.1% |   0.0633 |
|       OK |   41 |   36.8 | 4.9% | 0.316 | 0.1 |       41 | 0.0% |      - |    - | 4.9% |   0.0000 |
| DEGRADED |  106 |  115.5 | 4.7% | 0.286 | 0.1 |      106 | 0.0% |   0.0% |    - | 4.8% |   0.0094 |
|      ALL |  226 |   65.3 | 6.2% | 0.322 | 0.1 |      226 | 7.1% |  16.7% | 2.7× | 5.9% |   0.0265 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |   22 |   97.4 | 22.7% | 0.520 | 0.2 |       22 | 60.0% |  42.9% | 1.9× | 13.3% |   0.3182 |
|      ALL |   22 |   97.4 | 22.7% | 0.520 | 0.2 |       22 | 60.0% |  42.9% | 1.9× | 13.3% |   0.3182 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |   22 |   97.4 | 18.2% | 0.529 | 0.2 |       22 | 50.0% | 100.0% | 5.5× | 10.0% |   0.0909 |
|      ALL |   22 |   97.4 | 18.2% | 0.529 | 0.2 |       22 | 50.0% | 100.0% | 5.5× | 10.0% |   0.0909 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |   22 |   97.4 | 4.5% | 0.367 | 0.1 |       22 | 0.0% |      - |    - | 4.5% |   0.0000 |
|      ALL |   22 |   97.4 | 4.5% | 0.367 | 0.1 |       22 | 0.0% |      - |    - | 4.5% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available