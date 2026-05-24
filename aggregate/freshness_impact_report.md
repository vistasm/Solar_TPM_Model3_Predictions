# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-05-24 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (100.0%) is 100.0% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (3.3%) is 2.5× the overall rate (1.3%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   30 |   12.8 | 10.0% | 0.455 | 0.1 |       29 | 100.0% |  20.0% | 1.9× | 0.0% |   0.5172 |
|       OK |   19 |   36.0 | 5.3% | 0.394 | 0.1 |       17 | 100.0% |  33.3% | 5.7× | 0.0% |   0.1765 |
| DEGRADED |   26 |  123.5 | 7.7% | 0.371 | 0.1 |       25 | 0.0% |   0.0% |    - | 10.0% |   0.2000 |
|      ALL |   75 |   57.0 | 8.0% | 0.410 | 0.1 |       71 | 66.7% |  17.4% | 2.1× | 4.2% |   0.3239 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   30 |   12.8 | 3.3% | 0.430 | 0.0 |       29 | 100.0% |  25.0% | 7.2× | 0.0% |   0.1379 |
|       OK |   19 |   36.0 | 0.0% | 0.331 | 0.0 |       17 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   26 |  123.5 | 0.0% | 0.304 | 0.0 |       25 |    - |   0.0% |    - | 0.0% |   0.0800 |
|      ALL |   75 |   57.0 | 1.3% | 0.361 | 0.0 |       71 | 100.0% |  16.7% | 11.8× | 0.0% |   0.0845 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   30 |   12.8 | 3.3% | 0.245 | 0.0 |       29 | 0.0% |   0.0% |    - | 3.7% |   0.0690 |
|       OK |   19 |   36.0 | 5.3% | 0.280 | 0.1 |       17 | 0.0% |      - |    - | 5.9% |   0.0000 |
| DEGRADED |   26 |  123.5 | 3.9% | 0.221 | 0.0 |       25 | 0.0% |   0.0% |    - | 4.2% |   0.0400 |
|      ALL |   75 |   57.0 | 4.0% | 0.245 | 0.0 |       71 | 0.0% |   0.0% |    - | 4.4% |   0.0423 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   12.0 | 21.4% | 0.516 | 0.2 |       13 | 100.0% |  42.9% | 1.9× | 0.0% |   0.5385 |
|       OK |    8 |   36.4 | 0.0% | 0.333 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    9 |   67.7 | 0.0% | 0.369 | 0.0 |        8 |    - |   0.0% |    - | 0.0% |   0.2500 |
|      ALL |   31 |   34.5 | 9.7% | 0.426 | 0.1 |       27 | 100.0% |  33.3% | 3.0× | 0.0% |   0.3333 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   12.0 | 7.1% | 0.493 | 0.1 |       13 | 100.0% |  50.0% | 6.5× | 0.0% |   0.1538 |
|       OK |    8 |   36.4 | 0.0% | 0.255 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    9 |   67.7 | 0.0% | 0.264 | 0.0 |        8 |    - |   0.0% |    - | 0.0% |   0.1250 |
|      ALL |   31 |   34.5 | 3.2% | 0.365 | 0.0 |       27 | 100.0% |  33.3% | 9.0× | 0.0% |   0.1111 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   12.0 | 0.0% | 0.261 | 0.0 |       13 |    - |   0.0% |    - | 0.0% |   0.0769 |
|       OK |    8 |   36.4 | 0.0% | 0.175 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    9 |   67.7 | 0.0% | 0.174 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   34.5 | 0.0% | 0.213 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available