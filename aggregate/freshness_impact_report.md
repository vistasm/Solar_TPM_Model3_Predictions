# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-04-23 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

✅ No anomalies detected. Insufficient data or metrics within normal range.

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   16 |   13.5 | 0.0% | 0.400 | 0.0 |       16 |    - |   0.0% |    - | 0.0% |   0.5000 |
|       OK |   11 |   35.7 | 9.1% | 0.438 | 0.1 |       11 | 100.0% |  33.3% | 3.7× | 0.0% |   0.2727 |
| DEGRADED |   17 |  153.0 | 11.8% | 0.373 | 0.1 |       14 | 0.0% |   0.0% |    - | 15.4% |   0.0714 |
|      ALL |   44 |   73.0 | 6.8% | 0.399 | 0.1 |       41 | 33.3% |   8.3% | 1.1× | 6.9% |   0.2927 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   16 |   13.5 | 0.0% | 0.375 | 0.0 |       16 |    - |   0.0% |    - | 0.0% |   0.1250 |
|       OK |   11 |   35.7 | 0.0% | 0.387 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   17 |  153.0 | 0.0% | 0.325 | 0.0 |       14 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   44 |   73.0 | 0.0% | 0.359 | 0.0 |       41 |    - |   0.0% |    - | 0.0% |   0.0488 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   16 |   13.5 | 6.2% | 0.232 | 0.1 |       16 | 0.0% |   0.0% |    - | 6.7% |   0.0625 |
|       OK |   11 |   35.7 | 9.1% | 0.357 | 0.1 |       11 | 0.0% |      - |    - | 9.1% |   0.0000 |
| DEGRADED |   17 |  153.0 | 5.9% | 0.245 | 0.1 |       14 | 0.0% |      - |    - | 7.1% |   0.0000 |
|      ALL |   44 |   73.0 | 6.8% | 0.268 | 0.1 |       41 | 0.0% |   0.0% |    - | 7.5% |   0.0244 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   11.6 | 0.0% | 0.392 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.5000 |
|       OK |    7 |   33.9 | 14.3% | 0.457 | 0.1 |        7 | 100.0% |  50.0% | 3.5× | 0.0% |   0.2857 |
| DEGRADED |   13 |  173.6 | 0.0% | 0.357 | 0.0 |       10 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   30 |   87.0 | 3.3% | 0.392 | 0.0 |       27 | 100.0% |  14.3% | 3.9× | 0.0% |   0.2593 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   11.6 | 0.0% | 0.387 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.2000 |
|       OK |    7 |   33.9 | 0.0% | 0.423 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |  173.6 | 0.0% | 0.322 | 0.0 |       10 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   30 |   87.0 | 0.0% | 0.367 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   11.6 | 10.0% | 0.255 | 0.1 |       10 | 0.0% |   0.0% |    - | 11.1% |   0.1000 |
|       OK |    7 |   33.9 | 14.3% | 0.327 | 0.1 |        7 | 0.0% |      - |    - | 14.3% |   0.0000 |
| DEGRADED |   13 |  173.6 | 0.0% | 0.177 | 0.0 |       10 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   30 |   87.0 | 6.7% | 0.238 | 0.1 |       27 | 0.0% |   0.0% |    - | 7.7% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available