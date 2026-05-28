# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-05-28 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (100.0%) is 100.0% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (3.3%) is 2.6× the overall rate (1.3%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   30 |   12.8 | 10.0% | 0.455 | 0.1 |       30 | 100.0% |  20.0% | 2.0× | 0.0% |   0.5000 |
|       OK |   19 |   36.0 | 5.3% | 0.394 | 0.1 |       19 | 100.0% |  33.3% | 6.3× | 0.0% |   0.1579 |
| DEGRADED |   30 |  120.8 | 13.3% | 0.395 | 0.1 |       26 | 0.0% |   0.0% |    - | 10.0% |   0.2308 |
|      ALL |   79 |   59.4 | 10.1% | 0.417 | 0.1 |       75 | 66.7% |  16.7% | 2.1× | 3.9% |   0.3200 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   30 |   12.8 | 3.3% | 0.430 | 0.0 |       30 | 100.0% |  25.0% | 7.5× | 0.0% |   0.1333 |
|       OK |   19 |   36.0 | 0.0% | 0.331 | 0.0 |       19 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   30 |  120.8 | 0.0% | 0.318 | 0.0 |       26 |    - |   0.0% |    - | 0.0% |   0.0769 |
|      ALL |   79 |   59.4 | 1.3% | 0.364 | 0.0 |       75 | 100.0% |  16.7% | 12.5× | 0.0% |   0.0800 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   30 |   12.8 | 3.3% | 0.245 | 0.0 |       30 | 0.0% |   0.0% |    - | 3.6% |   0.0667 |
|       OK |   19 |   36.0 | 5.3% | 0.280 | 0.1 |       19 | 0.0% |      - |    - | 5.3% |   0.0000 |
| DEGRADED |   30 |  120.8 | 3.3% | 0.249 | 0.0 |       26 | 0.0% |   0.0% |    - | 4.0% |   0.0385 |
|      ALL |   79 |   59.4 | 3.8% | 0.255 | 0.0 |       75 | 0.0% |   0.0% |    - | 4.2% |   0.0400 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   14.0 | 0.0% | 0.433 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.3000 |
|       OK |    8 |   36.4 | 0.0% | 0.333 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |   78.6 | 15.4% | 0.424 | 0.1 |        9 |    - |   0.0% |    - | 0.0% |   0.3333 |
|      ALL |   31 |   46.9 | 6.5% | 0.404 | 0.1 |       27 |    - |   0.0% |    - | 0.0% |   0.2222 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   14.0 | 0.0% | 0.371 | 0.0 |       10 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    8 |   36.4 | 0.0% | 0.255 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |   78.6 | 0.0% | 0.308 | 0.0 |        9 |    - |   0.0% |    - | 0.0% |   0.1111 |
|      ALL |   31 |   46.9 | 0.0% | 0.315 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0370 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   14.0 | 0.0% | 0.201 | 0.0 |       10 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    8 |   36.4 | 0.0% | 0.175 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |   78.6 | 0.0% | 0.255 | 0.0 |        9 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   46.9 | 0.0% | 0.217 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available