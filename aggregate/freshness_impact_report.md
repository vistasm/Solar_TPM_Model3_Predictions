# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-11-10 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (68.4%) is 35.1% HIGHER than DEGRADED (33.3%) — fresher data is helping
🟢 **X+**: FRESH precision (14.3%) is 14.3% HIGHER than DEGRADED (0.0%) — fresher data is helping

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   82 |   12.6 | 25.6% | 0.521 | 0.3 |       80 | 68.4% |  36.1% | 1.5× | 13.6% |   0.4500 |
|       OK |   43 |   36.7 | 16.3% | 0.436 | 0.2 |       41 | 40.0% |  40.0% | 3.3× | 8.3% |   0.1220 |
| DEGRADED |  121 |  116.7 | 9.9% | 0.402 | 0.1 |      121 | 33.3% |  17.4% | 1.8× | 8.2% |   0.1901 |
|      ALL |  246 |   68.0 | 16.3% | 0.447 | 0.2 |      242 | 52.8% |  29.7% | 2.0× | 9.6% |   0.2645 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   82 |   12.6 | 12.2% | 0.507 | 0.1 |       80 | 50.0% |  30.8% | 3.1× | 6.0% |   0.1625 |
|       OK |   43 |   36.7 | 4.7% | 0.374 | 0.1 |       41 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |  121 |  116.7 | 3.3% | 0.343 | 0.0 |      121 | 50.0% |  40.0% | 12.1× | 1.7% |   0.0413 |
|      ALL |  246 |   68.0 | 6.5% | 0.403 | 0.1 |      242 | 50.0% |  33.3% | 6.7× | 2.7% |   0.0744 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   82 |   12.6 | 8.5% | 0.388 | 0.1 |       80 | 14.3% |  20.0% | 2.3× | 8.0% |   0.0625 |
|       OK |   43 |   36.7 | 4.7% | 0.339 | 0.1 |       41 | 0.0% |      - |    - | 4.9% |   0.0000 |
| DEGRADED |  121 |  116.7 | 4.1% | 0.275 | 0.0 |      121 | 0.0% |   0.0% |    - | 4.2% |   0.0083 |
|      ALL |  246 |   68.0 | 5.7% | 0.324 | 0.1 |      242 | 7.1% |  16.7% | 2.9× | 5.5% |   0.0248 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    3 |   10.9 | 100.0% | 0.898 | 1.0 |        1 | 0.0% |      - |    - | 100.0% |   0.0000 |
|       OK |    2 |   35.0 | 100.0% | 0.893 | 1.0 |        0 |    - |      - |    - |   - |        - |
| DEGRADED |   26 |  113.5 | 7.7% | 0.411 | 0.1 |       26 | 0.0% |   0.0% |    - | 8.7% |   0.1154 |
|      ALL |   31 |   98.5 | 22.6% | 0.489 | 0.2 |       27 | 0.0% |   0.0% |    - | 12.5% |   0.1111 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    3 |   10.9 | 100.0% | 0.913 | 1.0 |        1 | 0.0% |      - |    - | 100.0% |   0.0000 |
|       OK |    2 |   35.0 | 100.0% | 0.917 | 1.0 |        0 |    - |      - |    - |   - |        - |
| DEGRADED |   26 |  113.5 | 3.9% | 0.395 | 0.0 |       26 | 0.0% |      - |    - | 3.9% |   0.0000 |
|      ALL |   31 |   98.5 | 19.4% | 0.479 | 0.2 |       27 | 0.0% |      - |    - | 7.4% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    3 |   10.9 | 0.0% | 0.776 | 0.0 |        1 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    2 |   35.0 | 0.0% | 0.817 | 0.0 |        0 |    - |      - |    - |   - |        - |
| DEGRADED |   26 |  113.5 | 0.0% | 0.280 | 0.0 |       26 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   98.5 | 0.0% | 0.362 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available