# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-11-08 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (72.2%) is 38.9% HIGHER than DEGRADED (33.3%) — fresher data is helping
🟢 **M5+**: FRESH precision (57.1%) is 7.1% HIGHER than DEGRADED (50.0%) — fresher data is helping
🟢 **X+**: FRESH precision (14.3%) is 14.3% HIGHER than DEGRADED (0.0%) — fresher data is helping

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   81 |   12.7 | 24.7% | 0.516 | 0.3 |       79 | 72.2% |  36.1% | 1.6× | 11.6% |   0.4557 |
|       OK |   42 |   36.8 | 14.3% | 0.424 | 0.1 |       41 | 40.0% |  40.0% | 3.3× | 8.3% |   0.1220 |
| DEGRADED |  121 |  116.7 | 9.9% | 0.402 | 0.1 |      120 | 33.3% |  18.2% | 1.8× | 8.2% |   0.1833 |
|      ALL |  244 |   68.4 | 15.6% | 0.444 | 0.2 |      240 | 54.3% |  30.2% | 2.1× | 9.0% |   0.2625 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   81 |   12.7 | 11.1% | 0.502 | 0.1 |       79 | 57.1% |  30.8% | 3.5× | 4.5% |   0.1646 |
|       OK |   42 |   36.8 | 2.4% | 0.360 | 0.0 |       41 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |  121 |  116.7 | 3.3% | 0.343 | 0.0 |      120 | 50.0% |  40.0% | 12.0× | 1.7% |   0.0417 |
|      ALL |  244 |   68.4 | 5.7% | 0.399 | 0.1 |      240 | 54.5% |  33.3% | 7.3× | 2.2% |   0.0750 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   81 |   12.7 | 8.6% | 0.383 | 0.1 |       79 | 14.3% |  20.0% | 2.3× | 8.1% |   0.0633 |
|       OK |   42 |   36.8 | 4.8% | 0.325 | 0.1 |       41 | 0.0% |      - |    - | 4.9% |   0.0000 |
| DEGRADED |  121 |  116.7 | 4.1% | 0.275 | 0.0 |      120 | 0.0% |   0.0% |    - | 4.2% |   0.0083 |
|      ALL |  244 |   68.4 | 5.7% | 0.319 | 0.1 |      240 | 7.1% |  16.7% | 2.9× | 5.6% |   0.0250 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    2 |   10.9 | 100.0% | 0.895 | 1.0 |        0 |    - |      - |    - |   - |        - |
|       OK |    1 |   35.0 | 100.0% | 0.849 | 1.0 |        0 |    - |      - |    - |   - |        - |
| DEGRADED |   28 |  112.4 | 14.3% | 0.445 | 0.1 |       27 | 50.0% |  50.0% | 3.4× | 8.7% |   0.1481 |
|      ALL |   31 |  103.3 | 22.6% | 0.487 | 0.2 |       27 | 50.0% |  50.0% | 3.4× | 8.7% |   0.1481 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    2 |   10.9 | 100.0% | 0.917 | 1.0 |        0 |    - |      - |    - |   - |        - |
|       OK |    1 |   35.0 | 100.0% | 0.894 | 1.0 |        0 |    - |      - |    - |   - |        - |
| DEGRADED |   28 |  112.4 | 10.7% | 0.432 | 0.1 |       27 | 33.3% | 100.0% | 9.0× | 7.7% |   0.0370 |
|      ALL |   31 |  103.3 | 19.4% | 0.479 | 0.2 |       27 | 33.3% | 100.0% | 9.0× | 7.7% |   0.0370 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    2 |   10.9 | 0.0% | 0.773 | 0.0 |        0 |    - |      - |    - |   - |        - |
|       OK |    1 |   35.0 | 0.0% | 0.698 | 0.0 |        0 |    - |      - |    - |   - |        - |
| DEGRADED |   28 |  112.4 | 0.0% | 0.308 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |  103.3 | 0.0% | 0.351 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available