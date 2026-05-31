# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-05-31 UTC
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
|       OK |   20 |   36.5 | 5.0% | 0.403 | 0.1 |       19 | 100.0% |  33.3% | 6.3× | 0.0% |   0.1579 |
| DEGRADED |   31 |  122.1 | 12.9% | 0.391 | 0.1 |       29 | 0.0% |   0.0% |    - | 13.0% |   0.2069 |
|      ALL |   82 |   60.0 | 9.8% | 0.415 | 0.1 |       78 | 57.1% |  16.7% | 1.9× | 5.6% |   0.3077 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   31 |   13.1 | 3.2% | 0.424 | 0.0 |       30 | 100.0% |  25.0% | 7.5× | 0.0% |   0.1333 |
|       OK |   20 |   36.5 | 0.0% | 0.332 | 0.0 |       19 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   31 |  122.1 | 0.0% | 0.314 | 0.0 |       29 |    - |   0.0% |    - | 0.0% |   0.0690 |
|      ALL |   82 |   60.0 | 1.2% | 0.360 | 0.0 |       78 | 100.0% |  16.7% | 13.0× | 0.0% |   0.0769 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   31 |   13.1 | 3.2% | 0.240 | 0.0 |       30 | 0.0% |   0.0% |    - | 3.6% |   0.0667 |
|       OK |   20 |   36.5 | 5.0% | 0.296 | 0.1 |       19 | 0.0% |      - |    - | 5.3% |   0.0000 |
| DEGRADED |   31 |  122.1 | 3.2% | 0.244 | 0.0 |       29 | 0.0% |   0.0% |    - | 3.6% |   0.0345 |
|      ALL |   82 |   60.0 | 3.7% | 0.255 | 0.0 |       78 | 0.0% |   0.0% |    - | 4.0% |   0.0385 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   13.9 | 0.0% | 0.348 | 0.0 |        8 |    - |   0.0% |    - | 0.0% |   0.2500 |
|       OK |    8 |   37.3 | 0.0% | 0.350 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   14 |   84.6 | 14.3% | 0.412 | 0.1 |       12 | 0.0% |   0.0% |    - | 11.1% |   0.2500 |
|      ALL |   31 |   51.9 | 6.5% | 0.377 | 0.1 |       27 | 0.0% |   0.0% |    - | 4.5% |   0.1852 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   13.9 | 0.0% | 0.281 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    8 |   37.3 | 0.0% | 0.255 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   14 |   84.6 | 0.0% | 0.301 | 0.0 |       12 |    - |   0.0% |    - | 0.0% |   0.0833 |
|      ALL |   31 |   51.9 | 0.0% | 0.283 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0370 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   13.9 | 0.0% | 0.181 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    8 |   37.3 | 0.0% | 0.239 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   14 |   84.6 | 0.0% | 0.242 | 0.0 |       12 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   51.9 | 0.0% | 0.224 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available