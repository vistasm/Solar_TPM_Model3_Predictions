# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-05-05 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (100.0%) is 100.0% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (4.2%) is 2.3× the overall rate (1.8%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   24 |   12.4 | 12.5% | 0.486 | 0.1 |       22 | 100.0% |  23.1% | 1.7× | 0.0% |   0.5909 |
|       OK |   13 |   35.4 | 7.7% | 0.429 | 0.1 |       12 | 100.0% |  33.3% | 4.0× | 0.0% |   0.2500 |
| DEGRADED |   19 |  144.8 | 10.5% | 0.379 | 0.1 |       18 | 0.0% |   0.0% |    - | 13.3% |   0.1667 |
|      ALL |   56 |   62.7 | 10.7% | 0.436 | 0.1 |       52 | 66.7% |  21.1% | 1.8× | 6.1% |   0.3654 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   24 |   12.4 | 4.2% | 0.472 | 0.0 |       22 | 100.0% |  25.0% | 5.5× | 0.0% |   0.1818 |
|       OK |   13 |   35.4 | 0.0% | 0.372 | 0.0 |       12 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   19 |  144.8 | 0.0% | 0.319 | 0.0 |       18 |    - |   0.0% |    - | 0.0% |   0.0556 |
|      ALL |   56 |   62.7 | 1.8% | 0.397 | 0.0 |       52 | 100.0% |  20.0% | 10.4× | 0.0% |   0.0962 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   24 |   12.4 | 4.2% | 0.262 | 0.0 |       22 | 0.0% |   0.0% |    - | 5.0% |   0.0909 |
|       OK |   13 |   35.4 | 7.7% | 0.335 | 0.1 |       12 | 0.0% |      - |    - | 8.3% |   0.0000 |
| DEGRADED |   19 |  144.8 | 5.3% | 0.229 | 0.1 |       18 | 0.0% |   0.0% |    - | 5.9% |   0.0556 |
|      ALL |   56 |   62.7 | 5.4% | 0.268 | 0.1 |       52 | 0.0% |   0.0% |    - | 6.1% |   0.0577 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   10.7 | 30.0% | 0.593 | 0.3 |        8 | 100.0% |  60.0% | 1.6× | 0.0% |   0.6250 |
|       OK |    5 |   34.5 | 20.0% | 0.449 | 0.2 |        4 | 100.0% | 100.0% | 4.0× | 0.0% |   0.2500 |
| DEGRADED |   15 |  160.5 | 0.0% | 0.367 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.1429 |
|      ALL |   30 |   89.6 | 13.3% | 0.456 | 0.1 |       26 | 100.0% |  50.0% | 3.2× | 0.0% |   0.3077 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   10.7 | 10.0% | 0.595 | 0.1 |        8 | 100.0% |  50.0% | 4.0× | 0.0% |   0.2500 |
|       OK |    5 |   34.5 | 0.0% | 0.361 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   15 |  160.5 | 0.0% | 0.315 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.0714 |
|      ALL |   30 |   89.6 | 3.3% | 0.416 | 0.0 |       26 | 100.0% |  33.3% | 8.7× | 0.0% |   0.1154 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   10.7 | 0.0% | 0.276 | 0.0 |        8 |    - |   0.0% |    - | 0.0% |   0.1250 |
|       OK |    5 |   34.5 | 20.0% | 0.316 | 0.2 |        4 | 0.0% |      - |    - | 25.0% |   0.0000 |
| DEGRADED |   15 |  160.5 | 0.0% | 0.166 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.0714 |
|      ALL |   30 |   89.6 | 3.3% | 0.228 | 0.0 |       26 | 0.0% |   0.0% |    - | 4.2% |   0.0769 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available