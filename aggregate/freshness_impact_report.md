# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-05-30 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (100.0%) is 100.0% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (3.2%) is 2.6× the overall rate (1.2%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   31 |   13.1 | 9.7% | 0.448 | 0.1 |       30 | 100.0% |  20.0% | 2.0× | 0.0% |   0.5000 |
|       OK |   19 |   36.0 | 5.3% | 0.394 | 0.1 |       19 | 100.0% |  33.3% | 6.3× | 0.0% |   0.1579 |
| DEGRADED |   31 |  122.1 | 12.9% | 0.391 | 0.1 |       28 | 0.0% |   0.0% |    - | 13.6% |   0.2143 |
|      ALL |   81 |   60.2 | 9.9% | 0.413 | 0.1 |       77 | 57.1% |  16.7% | 1.8× | 5.7% |   0.3117 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   31 |   13.1 | 3.2% | 0.424 | 0.0 |       30 | 100.0% |  25.0% | 7.5× | 0.0% |   0.1333 |
|       OK |   19 |   36.0 | 0.0% | 0.331 | 0.0 |       19 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   31 |  122.1 | 0.0% | 0.314 | 0.0 |       28 |    - |   0.0% |    - | 0.0% |   0.0714 |
|      ALL |   81 |   60.2 | 1.2% | 0.360 | 0.0 |       77 | 100.0% |  16.7% | 12.8× | 0.0% |   0.0779 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   31 |   13.1 | 3.2% | 0.240 | 0.0 |       30 | 0.0% |   0.0% |    - | 3.6% |   0.0667 |
|       OK |   19 |   36.0 | 5.3% | 0.280 | 0.1 |       19 | 0.0% |      - |    - | 5.3% |   0.0000 |
| DEGRADED |   31 |  122.1 | 3.2% | 0.244 | 0.0 |       28 | 0.0% |   0.0% |    - | 3.7% |   0.0357 |
|      ALL |   81 |   60.2 | 3.7% | 0.251 | 0.0 |       77 | 0.0% |   0.0% |    - | 4.0% |   0.0390 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   13.9 | 0.0% | 0.348 | 0.0 |        8 |    - |   0.0% |    - | 0.0% |   0.2500 |
|       OK |    8 |   36.4 | 0.0% | 0.333 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   14 |   84.6 | 14.3% | 0.412 | 0.1 |       11 | 0.0% |   0.0% |    - | 12.5% |   0.2727 |
|      ALL |   31 |   51.6 | 6.5% | 0.373 | 0.1 |       27 | 0.0% |   0.0% |    - | 4.5% |   0.1852 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   13.9 | 0.0% | 0.281 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    8 |   36.4 | 0.0% | 0.255 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   14 |   84.6 | 0.0% | 0.301 | 0.0 |       11 |    - |   0.0% |    - | 0.0% |   0.0909 |
|      ALL |   31 |   51.6 | 0.0% | 0.283 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0370 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   13.9 | 0.0% | 0.181 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    8 |   36.4 | 0.0% | 0.175 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   14 |   84.6 | 0.0% | 0.242 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   51.6 | 0.0% | 0.207 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available