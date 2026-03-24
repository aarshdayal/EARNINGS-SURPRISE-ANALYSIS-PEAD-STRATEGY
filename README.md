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

