# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-11-06 UTC
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
🟡 **M5+**: FRESH alert rate (10.0%) is 2.0× the overall rate (5.0%) — score distribution shift detected
🟢 **X+**: FRESH precision (14.3%) is 14.3% HIGHER than DEGRADED (0.0%) — fresher data is helping

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   80 |   12.7 | 23.8% | 0.512 | 0.3 |       79 | 72.2% |  36.1% | 1.6× | 11.6% |   0.4557 |
|       OK |   41 |   36.8 | 12.2% | 0.414 | 0.1 |       41 | 40.0% |  40.0% | 3.3× | 8.3% |   0.1220 |
| DEGRADED |  121 |  116.7 | 9.9% | 0.402 | 0.1 |      118 | 33.3% |  18.2% | 1.8× | 8.3% |   0.1864 |
|      ALL |  242 |   68.8 | 14.9% | 0.440 | 0.2 |      238 | 54.3% |  30.2% | 2.0× | 9.1% |   0.2647 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   80 |   12.7 | 10.0% | 0.498 | 0.1 |       79 | 57.1% |  30.8% | 3.5× | 4.5% |   0.1646 |
|       OK |   41 |   36.8 | 0.0% | 0.347 | 0.0 |       41 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |  121 |  116.7 | 3.3% | 0.343 | 0.0 |      118 | 50.0% |  40.0% | 11.8× | 1.8% |   0.0424 |
|      ALL |  242 |   68.8 | 5.0% | 0.395 | 0.1 |      238 | 54.5% |  33.3% | 7.2× | 2.3% |   0.0756 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   80 |   12.7 | 8.8% | 0.379 | 0.1 |       79 | 14.3% |  20.0% | 2.3× | 8.1% |   0.0633 |
|       OK |   41 |   36.8 | 4.9% | 0.316 | 0.1 |       41 | 0.0% |      - |    - | 4.9% |   0.0000 |
| DEGRADED |  121 |  116.7 | 4.1% | 0.275 | 0.0 |      118 | 0.0% |   0.0% |    - | 4.3% |   0.0085 |
|      ALL |  242 |   68.8 | 5.8% | 0.316 | 0.1 |      238 | 7.1% |  16.7% | 2.8× | 5.6% |   0.0252 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    1 |   11.0 | 100.0% | 0.921 | 1.0 |        0 |    - |      - |    - |   - |        - |
| DEGRADED |   30 |  111.4 | 16.7% | 0.472 | 0.2 |       27 | 60.0% |  60.0% | 3.2× | 9.1% |   0.1852 |
|      ALL |   31 |  108.1 | 19.4% | 0.487 | 0.2 |       27 | 60.0% |  60.0% | 3.2× | 9.1% |   0.1852 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    1 |   11.0 | 100.0% | 0.956 | 1.0 |        0 |    - |      - |    - |   - |        - |
| DEGRADED |   30 |  111.4 | 13.3% | 0.461 | 0.1 |       27 | 50.0% | 100.0% | 6.8× | 8.0% |   0.0741 |
|      ALL |   31 |  108.1 | 16.1% | 0.477 | 0.2 |       27 | 50.0% | 100.0% | 6.8× | 8.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    1 |   11.0 | 0.0% | 0.861 | 0.0 |        0 |    - |      - |    - |   - |        - |
| DEGRADED |   30 |  111.4 | 0.0% | 0.315 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |  108.1 | 0.0% | 0.333 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available