# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-06-21 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (75.0%) is 75.0% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (2.4%) is 2.5× the overall rate (1.0%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   41 |   12.9 | 9.8% | 0.443 | 0.1 |       39 | 75.0% |  17.6% | 1.7× | 4.5% |   0.4359 |
|       OK |   24 |   37.4 | 4.2% | 0.389 | 0.0 |       24 | 100.0% |  33.3% | 8.0× | 0.0% |   0.1250 |
| DEGRADED |   38 |  116.2 | 10.5% | 0.389 | 0.1 |       36 | 0.0% |   0.0% |    - | 14.8% |   0.2500 |
|      ALL |  103 |   56.7 | 8.7% | 0.411 | 0.1 |       99 | 44.4% |  13.8% | 1.5× | 7.1% |   0.2929 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   41 |   12.9 | 2.4% | 0.427 | 0.0 |       39 | 100.0% |  20.0% | 7.8× | 0.0% |   0.1282 |
|       OK |   24 |   37.4 | 0.0% | 0.321 | 0.0 |       24 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   38 |  116.2 | 0.0% | 0.316 | 0.0 |       36 |    - |   0.0% |    - | 0.0% |   0.0833 |
|      ALL |  103 |   56.7 | 1.0% | 0.362 | 0.0 |       99 | 100.0% |  12.5% | 12.4× | 0.0% |   0.0808 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   41 |   12.9 | 4.9% | 0.286 | 0.1 |       39 | 0.0% |   0.0% |    - | 5.6% |   0.0769 |
|       OK |   24 |   37.4 | 8.3% | 0.307 | 0.1 |       24 | 0.0% |      - |    - | 8.3% |   0.0000 |
| DEGRADED |   38 |  116.2 | 5.3% | 0.275 | 0.1 |       36 | 0.0% |   0.0% |    - | 5.7% |   0.0278 |
|      ALL |  103 |   56.7 | 5.8% | 0.287 | 0.1 |       99 | 0.0% |   0.0% |    - | 6.3% |   0.0404 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   13.7 | 8.3% | 0.404 | 0.1 |       10 | 0.0% |   0.0% |    - | 12.5% |   0.2000 |
|       OK |    6 |   42.7 | 0.0% | 0.401 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |   97.8 | 15.4% | 0.431 | 0.1 |       11 | 0.0% |   0.0% |    - | 28.6% |   0.3636 |
|      ALL |   31 |   54.6 | 9.7% | 0.415 | 0.1 |       27 | 0.0% |   0.0% |    - | 14.3% |   0.2222 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   13.7 | 0.0% | 0.399 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.1000 |
|       OK |    6 |   42.7 | 0.0% | 0.312 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |   97.8 | 0.0% | 0.340 | 0.0 |       11 |    - |   0.0% |    - | 0.0% |   0.0909 |
|      ALL |   31 |   54.6 | 0.0% | 0.357 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   13.7 | 8.3% | 0.372 | 0.1 |       10 | 0.0% |   0.0% |    - | 11.1% |   0.1000 |
|       OK |    6 |   42.7 | 16.7% | 0.451 | 0.2 |        6 | 0.0% |      - |    - | 16.7% |   0.0000 |
| DEGRADED |   13 |   97.8 | 7.7% | 0.396 | 0.1 |       11 | 0.0% |      - |    - | 9.1% |   0.0000 |
|      ALL |   31 |   54.6 | 9.7% | 0.397 | 0.1 |       27 | 0.0% |   0.0% |    - | 11.5% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available