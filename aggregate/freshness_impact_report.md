# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-09-29 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (72.2%) is 55.5% HIGHER than DEGRADED (16.7%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (8.9%) is 2.5× the overall rate (3.5%) — score distribution shift detected
🟢 **X+**: FRESH precision (14.3%) is 14.3% HIGHER than DEGRADED (0.0%) — fresher data is helping

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   79 |   12.7 | 22.8% | 0.507 | 0.3 |       79 | 72.2% |  36.1% | 1.6× | 11.6% |   0.4557 |
|       OK |   41 |   36.8 | 12.2% | 0.414 | 0.1 |       41 | 40.0% |  40.0% | 3.3× | 8.3% |   0.1220 |
| DEGRADED |   78 |  122.0 | 7.7% | 0.387 | 0.1 |       74 | 16.7% |   6.7% | 0.8× | 8.5% |   0.2027 |
|      ALL |  198 |   60.8 | 14.6% | 0.440 | 0.2 |      194 | 55.2% |  28.6% | 1.9× | 9.4% |   0.2887 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   79 |   12.7 | 8.9% | 0.492 | 0.1 |       79 | 57.1% |  30.8% | 3.5× | 4.5% |   0.1646 |
|       OK |   41 |   36.8 | 0.0% | 0.347 | 0.0 |       41 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   78 |  122.0 | 0.0% | 0.315 | 0.0 |       74 |    - |   0.0% |    - | 0.0% |   0.0405 |
|      ALL |  198 |   60.8 | 3.5% | 0.392 | 0.0 |      194 | 57.1% |  25.0% | 6.9× | 1.7% |   0.0825 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   79 |   12.7 | 8.9% | 0.373 | 0.1 |       79 | 14.3% |  20.0% | 2.3× | 8.1% |   0.0633 |
|       OK |   41 |   36.8 | 4.9% | 0.316 | 0.1 |       41 | 0.0% |      - |    - | 4.9% |   0.0000 |
| DEGRADED |   78 |  122.0 | 3.9% | 0.261 | 0.0 |       74 | 0.0% |   0.0% |    - | 4.1% |   0.0135 |
|      ALL |  198 |   60.8 | 6.1% | 0.317 | 0.1 |      194 | 8.3% |  16.7% | 2.7× | 5.9% |   0.0309 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   14.2 | 11.1% | 0.341 | 0.1 |        9 | 100.0% |  33.3% | 3.0× | 0.0% |   0.3333 |
|       OK |    5 |   35.3 | 0.0% | 0.330 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   15 |  145.9 | 0.0% | 0.298 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   29 |   85.9 | 3.5% | 0.317 | 0.0 |       25 | 100.0% |  33.3% | 8.3× | 0.0% |   0.1200 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   14.2 | 0.0% | 0.274 | 0.0 |        9 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    5 |   35.3 | 0.0% | 0.227 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   15 |  145.9 | 0.0% | 0.206 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   29 |   85.9 | 0.0% | 0.231 | 0.0 |       25 |    - |      - |    - | 0.0% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   14.2 | 11.1% | 0.362 | 0.1 |        9 | 0.0% |      - |    - | 11.1% |   0.0000 |
|       OK |    5 |   35.3 | 0.0% | 0.272 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   15 |  145.9 | 0.0% | 0.138 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   29 |   85.9 | 3.5% | 0.231 | 0.0 |       25 | 0.0% |      - |    - | 4.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available