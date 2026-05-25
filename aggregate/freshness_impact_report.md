# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-05-25 UTC
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
|       OK |   19 |   36.0 | 5.3% | 0.394 | 0.1 |       18 | 100.0% |  33.3% | 6.0× | 0.0% |   0.1667 |
| DEGRADED |   27 |  121.4 | 11.1% | 0.379 | 0.1 |       25 | 0.0% |   0.0% |    - | 10.0% |   0.2000 |
|      ALL |   76 |   57.2 | 9.2% | 0.413 | 0.1 |       72 | 66.7% |  17.4% | 2.1× | 4.1% |   0.3194 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   30 |   12.8 | 3.3% | 0.430 | 0.0 |       29 | 100.0% |  25.0% | 7.2× | 0.0% |   0.1379 |
|       OK |   19 |   36.0 | 0.0% | 0.331 | 0.0 |       18 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   27 |  121.4 | 0.0% | 0.312 | 0.0 |       25 |    - |   0.0% |    - | 0.0% |   0.0800 |
|      ALL |   76 |   57.2 | 1.3% | 0.363 | 0.0 |       72 | 100.0% |  16.7% | 12.0× | 0.0% |   0.0833 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   30 |   12.8 | 3.3% | 0.245 | 0.0 |       29 | 0.0% |   0.0% |    - | 3.7% |   0.0690 |
|       OK |   19 |   36.0 | 5.3% | 0.280 | 0.1 |       18 | 0.0% |      - |    - | 5.6% |   0.0000 |
| DEGRADED |   27 |  121.4 | 3.7% | 0.227 | 0.0 |       25 | 0.0% |   0.0% |    - | 4.2% |   0.0400 |
|      ALL |   76 |   57.2 | 4.0% | 0.248 | 0.0 |       72 | 0.0% |   0.0% |    - | 4.3% |   0.0417 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   12.6 | 15.4% | 0.496 | 0.1 |       12 | 100.0% |  33.3% | 2.0× | 0.0% |   0.5000 |
|       OK |    8 |   36.4 | 0.0% | 0.333 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   10 |   67.7 | 10.0% | 0.391 | 0.1 |        8 |    - |   0.0% |    - | 0.0% |   0.2500 |
|      ALL |   31 |   36.5 | 9.7% | 0.420 | 0.1 |       27 | 100.0% |  25.0% | 3.4× | 0.0% |   0.2963 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   12.6 | 7.7% | 0.467 | 0.1 |       12 | 100.0% | 100.0% | 12.0× | 0.0% |   0.0833 |
|       OK |    8 |   36.4 | 0.0% | 0.255 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   10 |   67.7 | 0.0% | 0.289 | 0.0 |        8 |    - |   0.0% |    - | 0.0% |   0.1250 |
|      ALL |   31 |   36.5 | 3.2% | 0.355 | 0.0 |       27 | 100.0% |  50.0% | 13.5× | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   12.6 | 0.0% | 0.247 | 0.0 |       12 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    8 |   36.4 | 0.0% | 0.175 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   10 |   67.7 | 0.0% | 0.197 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   36.5 | 0.0% | 0.212 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available