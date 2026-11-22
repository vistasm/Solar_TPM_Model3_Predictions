# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-11-22 UTC
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
|    FRESH |   87 |   12.5 | 24.1% | 0.525 | 0.3 |       86 | 66.7% |  36.8% | 1.5× | 14.6% |   0.4419 |
|       OK |   47 |   36.3 | 14.9% | 0.433 | 0.1 |       45 | 42.9% |  50.0% | 3.2× | 10.3% |   0.1333 |
| DEGRADED |  124 |  115.3 | 10.5% | 0.402 | 0.1 |      123 | 38.5% |  20.8% | 2.0× | 8.1% |   0.1951 |
|      ALL |  258 |   66.3 | 15.9% | 0.449 | 0.2 |      254 | 53.7% |  32.4% | 2.0× | 10.2% |   0.2677 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   87 |   12.5 | 11.5% | 0.508 | 0.1 |       86 | 40.0% |  30.8% | 2.6× | 8.2% |   0.1512 |
|       OK |   47 |   36.3 | 4.3% | 0.372 | 0.0 |       45 | 0.0% |      - |    - | 4.4% |   0.0000 |
| DEGRADED |  124 |  115.3 | 4.0% | 0.344 | 0.0 |      123 | 40.0% |  40.0% | 9.8× | 2.5% |   0.0406 |
|      ALL |  258 |   66.3 | 6.6% | 0.404 | 0.1 |      254 | 35.3% |  33.3% | 5.0× | 4.7% |   0.0709 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   87 |   12.5 | 9.2% | 0.394 | 0.1 |       86 | 12.5% |  20.0% | 2.1× | 8.6% |   0.0581 |
|       OK |   47 |   36.3 | 4.3% | 0.329 | 0.0 |       45 | 0.0% |      - |    - | 4.4% |   0.0000 |
| DEGRADED |  124 |  115.3 | 4.0% | 0.275 | 0.0 |      123 | 0.0% |   0.0% |    - | 4.1% |   0.0081 |
|      ALL |  258 |   66.3 | 5.8% | 0.325 | 0.1 |      254 | 6.7% |  16.7% | 2.8× | 5.7% |   0.0236 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   10.7 | 37.5% | 0.709 | 0.4 |        7 | 33.3% |  50.0% | 1.2× | 40.0% |   0.2857 |
|       OK |    6 |   33.2 | 33.3% | 0.559 | 0.3 |        4 | 50.0% | 100.0% | 2.0× | 33.3% |   0.2500 |
| DEGRADED |   17 |  115.3 | 5.9% | 0.322 | 0.1 |       16 | 100.0% |  50.0% | 8.0× | 0.0% |   0.1250 |
|      ALL |   31 |   72.4 | 19.4% | 0.468 | 0.2 |       27 | 50.0% |  60.0% | 2.7× | 13.6% |   0.1852 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   10.7 | 37.5% | 0.663 | 0.4 |        7 | 0.0% |      - |    - | 42.9% |   0.0000 |
|       OK |    6 |   33.2 | 33.3% | 0.540 | 0.3 |        4 | 0.0% |      - |    - | 50.0% |   0.0000 |
| DEGRADED |   17 |  115.3 | 5.9% | 0.240 | 0.1 |       16 | 0.0% |      - |    - | 6.2% |   0.0000 |
|      ALL |   31 |   72.4 | 19.4% | 0.407 | 0.2 |       27 | 0.0% |      - |    - | 22.2% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   10.7 | 12.5% | 0.606 | 0.1 |        7 | 0.0% |      - |    - | 14.3% |   0.0000 |
|       OK |    6 |   33.2 | 0.0% | 0.424 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   17 |  115.3 | 0.0% | 0.214 | 0.0 |       16 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   72.4 | 3.2% | 0.356 | 0.0 |       27 | 0.0% |      - |    - | 3.7% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available