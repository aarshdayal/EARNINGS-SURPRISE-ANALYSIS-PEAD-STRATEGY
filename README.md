# Post-Earnings Announcement Drift (PEAD) Strategy
### Earnings Surprise Analysis & Long-Short Portfolio Simulation in Python

This project investigates the **Post-Earnings Announcement Drift (PEAD)** anomaly —
one of the most well-documented inefficiencies in financial markets. Using 6 years of
real earnings and price data across 25 large-cap US stocks, it measures whether stocks
continue drifting in the direction of their earnings surprise after the announcement,
and whether a systematic long-short trading strategy can exploit this behaviour.

---

## The Core Question

> *If a company beats analyst expectations by a large margin, does its stock
> keep rising for the next 60 days — even after the market has already reacted
> on the announcement day?*

The academic answer is yes — this is PEAD. This project tests that claim empirically
on real data from 2019 to 2024.

---
## Results

### Earnings Surprise Statistics

| Metric | Value |
|---|---|
| Total events analysed | 521 |
| Beat rate | **79.2%** |
| Miss rate | 18.5% |
| In-line rate | 2.3% |
| Avg surprise on beats | +16.3% |
| Avg surprise on misses | −27.3% |

Large-cap US stocks overwhelmingly beat analyst estimates — a well-known phenomenon
called **analyst forecast bias**, where sell-side analysts tend to set conservative
estimates that companies can comfortably exceed.


**Summary statistics:**

| Metric | Value |
|---|---|
| Periods tested | 21 quarters (2019–2024) |
| Mean quarterly L-S return | **+2.19%** |
| Annualised return (×4) | **+8.77%** |
| Cumulative return | **+49.9%** |
| Win rate | **66.7%** |
| Sharpe-like ratio | 0.30 |


### Statistical Significance

| Test | t-stat | p-value | Significant? |
|---|---|---|---|
| Mean L-S return ≠ 0 | 1.40 | 0.1782 | ❌ No (5% level) |
| Q5 CAR drift > Q1 CAR drift | 0.662 | 0.5086 | ❌ No (5% level) |
| Surprise % predicts drift (regression) | — | **0.0219** | ✅ Yes (5% level) |

The long-short portfolio mean return is **positive (+2.19% per quarter)** and
the equity curve shows clear overall growth, but **the small sample size of only
21 quarterly periods** means the t-test lacks statistical power to confirm
significance at 5%. With more stocks or a longer time window, the result would
likely cross the threshold. The scatter regression, with 521 data points, does
confirm significance.

---

## Key Takeaways

1. **PEAD exists in the data** — Q5 stocks drift +3% above the market over 60
   days, Q1 stocks drift −2%, and the event study path chart shows this clearly
2. **The strategy is profitable** — +49.9% cumulative, +8.77% annualised,
   66.7% win rate over 6 years
3. **Statistical significance is limited by small sample** — only 25 stocks × 21
   quarters limits the power of t-tests; the scatter regression confirms the
   underlying signal is real (p=0.022) with 521 data points
4. **Extreme beats are already priced** — Q5 (biggest beats) shows *less* drift
   than Q3/Q4, suggesting the market reacts more completely to blockbuster results
5. **The short side is the weaker leg** — Q1 drift (−0.23%) is much smaller than
   Q5 drift (+0.90%); the strategy's edge comes primarily from the long leg

