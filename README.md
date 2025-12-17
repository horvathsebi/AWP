# Impact of Arbitrage Frictions on Hedging Effectiveness: CSI 300 vs. S&P 500

## Project Overview
This repository contains the quantitative analysis framework for my academic dissertation: **"The Impact of Arbitrage Frictions on Hedging Effectiveness in the CSI 300 Futures Market."**

The project investigates how market frictions, specifically the regulatory framework implemented to curb speculative trading activity, impact the ability to hedge effectively in the Chinese equity market (CSI 300) compared to a mature benchmark market (US S&P 500). By applying advanced econometric models to time-series data (2017–2025), the study quantifies Hedging Effectiveness (HE) and tests for structural breaks caused by arbitrage limits.

## Key Research Questions
The analysis was designed to test four specific hypotheses regarding the Limits to Arbitrage theory:

1.  **The Broken Feedback Loop:** Does the CSI 300 lack the self-correcting liquidity-pricing feedback loop found in efficient markets (S&P 500)? Specifically, does illiquidity fail to "Granger-cause" price corrections in China?
2.  **Hierarchy of Risks:** Is **Basis Risk** (pricing error) a more significant driver of hedging failure than **Liquidity Risk** in restricted markets? (Contrasting with efficient markets where liquidity is usually the primary constraint).
3.  **Asymmetric Frictions:** Do restrictions cause **asymmetric hedging risks**? Specifically, is Hedging Effectiveness damaged more severely during Contango (Positive Basis) or Backwardation (negative basis)?
4.  **Threshold Effects:** Is the relationship non-linear? Does the market exhibit a tipping point where regulatory frictions cause a disproportionate collapse in hedging performance?

## Methodology & Models
The core analysis is performed in `main.ipynb`. The econometric pipeline includes:

### 1. Data Processing
- Alignment of high-frequency spot and futures time-series data (CSI 300 & S&P 500).
- Calculation of basis spreads, log-returns, and Amihud illiquidity metrics.
- **Stationarity Testing:** Implementation of Augmented Dickey-Fuller (ADF) tests to ensure time-series validity.

### 2. Econometric Strategy
Four distinct regression models were constructed to test the hypotheses:

* **Granger Causality Tests:** To statistically prove the absence of a two-way feedback loop between liquidity and basis in the CSI 300.
* **Baseline Regression:** To establish a base causality between absolute basis, illiquidity and their impact on HE.
* **Asymmetric Regression:** To quantify the differential impact of positive basis shocks vs. negative basis shocks.
* **Threshold Regression:** To identify non-linearities and test if frictions become "fragility multipliers" during high-stress market regimes.

## Tech
* **Python:** Core logic and statistical programming.
* **Pandas/Numpy:** Time-series manipulation.
* **Statsmodels:** Advanced econometric modeling (OLS, ADL, Granger Causality).
* **Matplotlib:** Visualization of hedging errors, basis volatility, and illiquidity comparisons.

## Summary of Findings
* **Broken Mechanism:** Granger Causality tests confirmed that while the S&P 500 exhibits a healthy bidirectional feedback loop, the CSI 300 lacks the mechanism where liquidity corrects pricing errors.
* **Asymmetry:** The Asymmetric Regression proved that a **Positive Basis** (Contango) is significantly more damaging to hedging effectiveness than a negative basis.
* **Regime Dependence:** The Threshold Regression identified a structural break at the 75th percentile. In normal regimes, frictions are negligible, but in stressed regimes, the negative impact of pricing errors **triples**, validating the "fragility multiplier" hypothesis, although pinpointing the exact no-arbitrage bound requires further research.

## Usage
To replicate the analysis:

1.  Clone the repo:
    ```bash
    git clone [https://github.com/horvathsebi/arbitrage-frictions-csi300.git](https://github.com/horvathsebi/arbitrage-frictions-csi300.git)
    ```
2.  Install dependencies:
    ```bash
    pip install pandas numpy matplotlib statsmodels scipy
    ```
3.  Run the Jupyter Notebook:
    ```bash
    jupyter notebook main.ipynb
    ```

## Dissertation Availability
**Dissertation Title:** *The Impact of Arbitrage Frictions on Hedging Effectiveness in the CSI 300 Futures Market*

**Status:** Submitted for Grading (December 2025)

> The full text of the dissertation currently **available upon request**.

## Author
**Sebestyén Horváth**

*BSc (Hons) Corporate Finance*

*University of Buckingham & IBS Budapest*

www.linkedin.com/in/sebestyén-horváth | h.sebi2004@gmail.com
