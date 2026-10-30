# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-10-30 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (72.2%) is 32.2% HIGHER than DEGRADED (40.0%) — fresher data is helping
🟢 **X+**: FRESH precision (14.3%) is 14.3% HIGHER than DEGRADED (0.0%) — fresher data is helping

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   79 |   12.7 | 22.8% | 0.507 | 0.3 |       79 | 72.2% |  36.1% | 1.6× | 11.6% |   0.4557 |
|       OK |   41 |   36.8 | 12.2% | 0.414 | 0.1 |       41 | 40.0% |  40.0% | 3.3× | 8.3% |   0.1220 |
| DEGRADED |   95 |  117.6 | 10.5% | 0.399 | 0.1 |       95 | 40.0% |  20.0% | 1.9× | 8.0% |   0.2105 |
|      ALL |  215 |   63.6 | 15.3% | 0.441 | 0.2 |      215 | 57.6% |  31.1% | 2.0× | 9.1% |   0.2837 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   79 |   12.7 | 8.9% | 0.492 | 0.1 |       79 | 57.1% |  30.8% | 3.5× | 4.5% |   0.1646 |
|       OK |   41 |   36.8 | 0.0% | 0.347 | 0.0 |       41 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   95 |  117.6 | 3.2% | 0.329 | 0.0 |       95 | 66.7% |  40.0% | 12.7× | 1.1% |   0.0526 |
|      ALL |  215 |   63.6 | 4.7% | 0.392 | 0.1 |      215 | 60.0% |  33.3% | 7.2× | 2.0% |   0.0837 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   79 |   12.7 | 8.9% | 0.373 | 0.1 |       79 | 14.3% |  20.0% | 2.3× | 8.1% |   0.0633 |
|       OK |   41 |   36.8 | 4.9% | 0.316 | 0.1 |       41 | 0.0% |      - |    - | 4.9% |   0.0000 |
| DEGRADED |   95 |  117.6 | 5.3% | 0.274 | 0.1 |       95 | 0.0% |   0.0% |    - | 5.3% |   0.0105 |
|      ALL |  215 |   63.6 | 6.5% | 0.318 | 0.1 |      215 | 7.1% |  16.7% | 2.6× | 6.2% |   0.0279 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |   11 |   97.3 | 27.3% | 0.478 | 0.3 |       11 | 100.0% |  60.0% | 2.2× | 0.0% |   0.4545 |
|      ALL |   11 |   97.3 | 27.3% | 0.478 | 0.3 |       11 | 100.0% |  60.0% | 2.2× | 0.0% |   0.4545 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |   11 |   97.3 | 27.3% | 0.417 | 0.3 |       11 | 66.7% | 100.0% | 3.7× | 11.1% |   0.1818 |
|      ALL |   11 |   97.3 | 27.3% | 0.417 | 0.3 |       11 | 66.7% | 100.0% | 3.7× | 11.1% |   0.1818 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |   11 |   97.3 | 9.1% | 0.338 | 0.1 |       11 | 0.0% |      - |    - | 9.1% |   0.0000 |
|      ALL |   11 |   97.3 | 9.1% | 0.338 | 0.1 |       11 | 0.0% |      - |    - | 9.1% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available