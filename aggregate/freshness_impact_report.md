# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-09-21 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (72.2%) is 55.5% HIGHER than DEGRADED (16.7%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (8.9%) is 2.4× the overall rate (3.7%) — score distribution shift detected
🟢 **X+**: FRESH precision (14.3%) is 14.3% HIGHER than DEGRADED (0.0%) — fresher data is helping

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   79 |   12.7 | 22.8% | 0.507 | 0.3 |       78 | 72.2% |  36.1% | 1.6× | 11.9% |   0.4615 |
|       OK |   41 |   36.8 | 12.2% | 0.414 | 0.1 |       40 | 40.0% |  40.0% | 3.2× | 8.6% |   0.1250 |
| DEGRADED |   70 |  119.6 | 8.6% | 0.393 | 0.1 |       68 | 16.7% |   6.7% | 0.8× | 9.4% |   0.2206 |
|      ALL |  190 |   57.3 | 15.3% | 0.445 | 0.2 |      186 | 55.2% |  28.6% | 1.8× | 10.0% |   0.3011 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   79 |   12.7 | 8.9% | 0.492 | 0.1 |       78 | 57.1% |  30.8% | 3.4× | 4.6% |   0.1667 |
|       OK |   41 |   36.8 | 0.0% | 0.347 | 0.0 |       40 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   70 |  119.6 | 0.0% | 0.323 | 0.0 |       68 |    - |   0.0% |    - | 0.0% |   0.0441 |
|      ALL |  190 |   57.3 | 3.7% | 0.398 | 0.0 |      186 | 57.1% |  25.0% | 6.6× | 1.8% |   0.0860 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   79 |   12.7 | 8.9% | 0.373 | 0.1 |       78 | 14.3% |  20.0% | 2.2× | 8.2% |   0.0641 |
|       OK |   41 |   36.8 | 4.9% | 0.316 | 0.1 |       40 | 0.0% |      - |    - | 5.0% |   0.0000 |
| DEGRADED |   70 |  119.6 | 4.3% | 0.271 | 0.0 |       68 | 0.0% |   0.0% |    - | 4.5% |   0.0147 |
|      ALL |  190 |   57.3 | 6.3% | 0.323 | 0.1 |      186 | 8.3% |  16.7% | 2.6× | 6.1% |   0.0323 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   13.5 | 38.5% | 0.468 | 0.5 |       12 | 60.0% |  60.0% | 1.4× | 28.6% |   0.4167 |
|       OK |    7 |   36.0 | 28.6% | 0.430 | 0.3 |        6 | 0.0% |      - |    - | 33.3% |   0.0000 |
| DEGRADED |    9 |  129.5 | 11.1% | 0.304 | 0.1 |        7 | 100.0% | 100.0% | 7.0× | 0.0% |   0.1429 |
|      ALL |   29 |   54.9 | 27.6% | 0.408 | 0.3 |       25 | 50.0% |  66.7% | 2.1× | 21.1% |   0.2400 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   13.5 | 0.0% | 0.429 | 0.0 |       12 |    - |   0.0% |    - | 0.0% |   0.0833 |
|       OK |    7 |   36.0 | 0.0% | 0.365 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    9 |  129.5 | 0.0% | 0.229 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   29 |   54.9 | 0.0% | 0.351 | 0.0 |       25 |    - |   0.0% |    - | 0.0% |   0.0400 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   13.5 | 7.7% | 0.399 | 0.1 |       12 | 0.0% |      - |    - | 8.3% |   0.0000 |
|       OK |    7 |   36.0 | 0.0% | 0.317 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    9 |  129.5 | 0.0% | 0.140 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   29 |   54.9 | 3.5% | 0.299 | 0.0 |       25 | 0.0% |      - |    - | 4.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available