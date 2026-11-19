# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-11-19 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (66.7%) is 28.2% HIGHER than DEGRADED (38.5%) — fresher data is helping
🟢 **X+**: FRESH precision (12.5%) is 12.5% HIGHER than DEGRADED (0.0%) — fresher data is helping

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   86 |   12.5 | 24.4% | 0.525 | 0.3 |       84 | 66.7% |  37.8% | 1.5× | 14.9% |   0.4405 |
|       OK |   46 |   36.3 | 15.2% | 0.438 | 0.1 |       44 | 42.9% |  50.0% | 3.1× | 10.5% |   0.1364 |
| DEGRADED |  123 |  115.8 | 10.6% | 0.404 | 0.1 |      123 | 38.5% |  20.8% | 2.0× | 8.1% |   0.1951 |
|      ALL |  255 |   66.6 | 16.1% | 0.451 | 0.2 |      251 | 53.7% |  32.8% | 2.0× | 10.3% |   0.2669 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   86 |   12.5 | 11.6% | 0.506 | 0.1 |       84 | 40.0% |  30.8% | 2.6× | 8.5% |   0.1548 |
|       OK |   46 |   36.3 | 4.3% | 0.376 | 0.0 |       44 | 0.0% |      - |    - | 4.5% |   0.0000 |
| DEGRADED |  123 |  115.8 | 4.1% | 0.346 | 0.0 |      123 | 40.0% |  40.0% | 9.8× | 2.5% |   0.0406 |
|      ALL |  255 |   66.6 | 6.7% | 0.405 | 0.1 |      251 | 35.3% |  33.3% | 4.9× | 4.7% |   0.0717 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   86 |   12.5 | 9.3% | 0.390 | 0.1 |       84 | 12.5% |  20.0% | 2.1× | 8.9% |   0.0595 |
|       OK |   46 |   36.3 | 4.3% | 0.334 | 0.0 |       44 | 0.0% |      - |    - | 4.5% |   0.0000 |
| DEGRADED |  123 |  115.8 | 4.1% | 0.277 | 0.0 |      123 | 0.0% |   0.0% |    - | 4.1% |   0.0081 |
|      ALL |  255 |   66.6 | 5.9% | 0.326 | 0.1 |      251 | 6.7% |  16.7% | 2.8× | 5.7% |   0.0239 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    7 |   10.1 | 42.9% | 0.730 | 0.4 |        5 | 33.3% | 100.0% | 1.7× | 50.0% |   0.2000 |
|       OK |    5 |   32.0 | 40.0% | 0.631 | 0.4 |        3 | 50.0% | 100.0% | 1.5× | 50.0% |   0.3333 |
| DEGRADED |   19 |  115.2 | 5.3% | 0.333 | 0.1 |       19 | 100.0% |  50.0% | 9.5× | 0.0% |   0.1053 |
|      ALL |   31 |   78.0 | 19.4% | 0.471 | 0.2 |       27 | 50.0% |  75.0% | 3.4× | 13.0% |   0.1481 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    7 |   10.1 | 42.9% | 0.662 | 0.4 |        5 | 0.0% |      - |    - | 60.0% |   0.0000 |
|       OK |    5 |   32.0 | 40.0% | 0.609 | 0.4 |        3 | 0.0% |      - |    - | 66.7% |   0.0000 |
| DEGRADED |   19 |  115.2 | 5.3% | 0.271 | 0.1 |       19 | 0.0% |      - |    - | 5.3% |   0.0000 |
|      ALL |   31 |   78.0 | 19.4% | 0.414 | 0.2 |       27 | 0.0% |      - |    - | 22.2% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    7 |   10.1 | 14.3% | 0.586 | 0.1 |        5 | 0.0% |      - |    - | 20.0% |   0.0000 |
|       OK |    5 |   32.0 | 0.0% | 0.489 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   19 |  115.2 | 0.0% | 0.232 | 0.0 |       19 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   78.0 | 3.2% | 0.353 | 0.0 |       27 | 0.0% |      - |    - | 3.7% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available