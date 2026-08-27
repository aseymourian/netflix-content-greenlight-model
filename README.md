# Netflix Content Greenlight Financial Model

A corporate finance and capital budgeting analysis evaluating three real Netflix content investment decisions using WACC, NPV, payback period, sensitivity analysis, and historical performance data. The model assesses whether publicly available financial and engagement data could support the investment decisions Netflix made for **Red Notice**, **Extraction 2**, and **The Super Mario Bros. Movie**.

## Executive Summary

This project applies corporate finance methodology to three structurally different Netflix content investment decisions:

* **Red Notice (2021):** Evaluates an original-content greenlight and backtests the investment against observed performance.
* **Extraction → Extraction 2:** Evaluates a franchise continuation decision and compares the model's results with the actual sequel outcome.
* **The Super Mario Bros. Movie:** Evaluates a licensing/streaming-rights acquisition, demonstrating how a structurally different investment decision affects the feasibility of traditional capital-budgeting analysis.

### Key Findings

* Built a **10.79% company-wide WACC** from Netflix's FY2025 10-K and Q2 2026 10-Q, including a CAPM-derived cost of equity of **11.11%**, a par-value-weighted cost of debt of **4.76% pre-tax / 3.91% after-tax**, and market-value capital weights of **95.6% equity / 4.4% debt**.
* Independently calculated Netflix's **1.526 beta** using a five-year OLS regression of monthly NFLX returns against the S&P 500 and cross-validated the result against vendor-cited benchmarks of approximately **1.49–1.71**.
* Tested a comparable-title forecasting model across eight Netflix originals. The model produced **R² = 0.031 and p = 0.677**, indicating that production budget provided little explanatory power for observed hours viewed. Rather than force an unsupported forecast, the analysis pivoted to a historical backtesting framework.
* Red Notice and Extraction produced **negative NPV within Netflix's disclosed 91-day measurement window**. The model treats these results as conservative floors rather than estimates of lifetime economic value.
* Mario's licensing cost could not be calculated because Netflix does not publicly disclose the title's acquisition cost or a sufficiently comparable transaction. The model explicitly documents the limitation rather than introducing an unsupported assumption.

## Investment Questions

The analysis was designed to answer three questions:

1. **Would the available public data have supported the investment decision?**
2. **How sensitive are the investment conclusions to changes in discount rates, revenue attribution, and measurement windows?**
3. **Where does the public-data methodology become too limited to support a defensible financial conclusion?**

## Financial Methodology

### 1. Weighted Average Cost of Capital

Netflix's company-wide WACC was calculated using:

**WACC = (E/V × Cost of Equity) + (D/V × After-Tax Cost of Debt)**

The model derives:

| Component              |      Result |
| ---------------------- | ----------: |
| Beta                   |       1.526 |
| Risk-free rate         | Model input |
| Equity risk premium    | Model input |
| Cost of equity         |      11.11% |
| Pre-tax cost of debt   |       4.76% |
| After-tax cost of debt |       3.91% |
| Equity weight          |       95.6% |
| Debt weight            |        4.4% |
| **WACC**               |  **10.79%** |

All financial inputs are sourced from Netflix SEC filings and documented in the workbook's Assumptions and README tabs.

### 2. Beta Estimation

Rather than relying exclusively on a vendor-reported beta, the model independently estimates beta using a **five-year OLS regression of monthly Netflix stock returns against S&P 500 returns**.

The resulting beta of **1.526** was compared against independently reported vendor benchmarks ranging from approximately **1.49 to 1.71**.

### 3. Cash Flow & Revenue Attribution

Because Netflix does not disclose title-level revenue attribution, the model derives a **Value per Hour** metric from Netflix's disclosed financial and engagement data.

The approach uses:

**Global blended ARPU ÷ average hours watched per member per month**

This provides a consistent framework for translating disclosed engagement into an estimated economic value without attempting to estimate title-level subscriber acquisition or retention that Netflix does not publicly disclose.

### 4. NPV & Payback Analysis

Each investment was evaluated using:

* Net Present Value (NPV)
* Payback Period
* Discounted cash-flow analysis
* Two-variable sensitivity analysis
* Historical performance backtesting where appropriate

## Investment Analysis

### Red Notice

**Decision Type:** Original content greenlight

The model evaluates Red Notice using publicly available production-cost and engagement data and compares the resulting financial performance against the original investment decision.

The analysis produced a negative NPV within the disclosed 91-day engagement window. Because the measurement window does not represent lifetime viewing, the result is treated as a **conservative floor rather than a definitive lifetime valuation**.

### Extraction → Extraction 2

**Decision Type:** Franchise continuation

The model evaluates whether the observed performance of Extraction provided sufficient evidence to support a sequel investment.

The analysis compares the financial framework with the actual performance of Extraction 2, providing a historical backtest of the decision rather than treating the model as a purely theoretical valuation exercise.

### The Super Mario Bros. Movie

**Decision Type:** Licensing / streaming-rights acquisition

Mario represents a structurally different investment because Netflix's acquisition cost is not publicly disclosed.

The model therefore does **not** invent a licensing cost or substitute an unreliable comparable. Instead, it documents why a conventional NPV/payback calculation cannot be responsibly completed using public information alone.

## Sensitivity Analysis

Sensitivity analysis tests how investment conclusions change when key assumptions vary.

### Red Notice & Extraction

Two-variable sensitivity analysis evaluates:

* Value per Hour
* Discount Rate

### Mario

Sensitivity analysis evaluates:

* Value per Hour
* Measurement Window

This approach separates uncertainty in the model's assumptions from uncertainty created by limitations in Netflix's public reporting.

## A Real-Data Methodology Finding

Netflix changed its public engagement reporting methodology in **November 2021**, moving from households reached within 28 days to hours viewed within 91 days.

This creates an important methodological limitation: titles released before the transition were not measured using the current 91-day hours-viewed methodology.

As a result, historical comparable-title datasets cannot simply combine older and newer engagement metrics without introducing measurement inconsistency.

The Super Mario Bros. Movie demonstrates the magnitude of this issue. Its first-eight-week viewing figure of approximately **6.5 million hours** was roughly 30 times smaller than its reported **195.3 million U.S. hours viewed during calendar year 2024 alone**, illustrating how a limited measurement window can materially understate lifetime viewing activity.

## Validation & Quality Assurance

The project emphasizes validation rather than simply producing financial outputs.

Key validation steps included:

* Independently calculating beta using OLS regression
* Cross-validating beta against external benchmarks
* Testing and rejecting an statistically insignificant comps-based forecasting model
* Cross-checking Value per Hour against an independently derived content cost-per-hour benchmark
* Testing investment conclusions under alternative discount rates and measurement assumptions
* Documenting unavailable inputs rather than replacing them with unsupported estimates
* Maintaining source and confidence documentation for every major assumption

The independently derived cost-per-hour benchmark produced a directionally consistent **approximately 2.65× relationship between estimated value per hour and platform-wide content cost per hour**, providing an additional reasonableness check on the revenue-attribution framework.

## Data Sources

Primary sources were prioritized wherever possible, including:

* Netflix FY2025 10-K
* Netflix Q2 2026 10-Q
* Netflix investor disclosures
* Netflix public engagement data
* SEC filings
* Historical market-price data
* Secondary sources used only for cross-validation where primary data was unavailable

Every major model input is documented in the workbook's **Assumptions** tab with its source and confidence tier.

## Skills Demonstrated

**Corporate Finance:** WACC · CAPM · Cost of Equity · Cost of Debt · NPV · Payback Period · Capital Budgeting · Sensitivity Analysis

**Financial Modeling:** Excel · Scenario Analysis · Cash Flow Modeling · Assumption Management · Financial Decision Support

**Statistical Analysis:** OLS Regression · Beta Estimation · R² · p-values · Confidence Intervals · Model Diagnostics

**Data & Research:** SEC Filings · Primary-Source Research · Financial Data Sourcing · Data Validation · Confidence Tiering

**Analytical Judgment:** Model Validation · Methodology Testing · Backtesting · Limitation Analysis · Evidence-Based Decision Making

## Repository Contents

### `01_cleaning_data_finance.xlsx`

The complete financial model containing:

* **Assumptions** — Long-format input table with source, confidence tier, and notes
* **Metrics** — Complete WACC build, beta regression, CAPM, cost of debt, and capital structure
* **Red Notice** — NPV, payback period, cash flow analysis, and investment evaluation
* **Extraction** — NPV, payback period, cash flow analysis, and franchise evaluation
* **Mario** — Investment analysis and sensitivity framework
* **Sensitivity** — Two-variable sensitivity analysis
* **Go or No Go Summary** — Final investment assessment and rationale
* **README** — Full sourcing documentation, methodology notes, confidence-tier definitions, and limitations

## Limitations

This model relies exclusively on publicly available information. Netflix's internal financial and engagement systems are not accessible externally, limiting the analysis in several areas, including:

* Title-level acquisition and production costs
* Subscriber acquisition and retention attributable to individual titles
* Lifetime engagement beyond disclosed measurement windows
* Consistent historical engagement metrics across reporting eras
* Internal investment hurdle rates and project-specific assumptions

These limitations are treated as part of the analysis rather than hidden assumptions.

A production finance or strategy team with access to internal Netflix data could substantially improve the model through more granular cost, engagement, subscriber, and lifetime-value information.

## Conclusion

The primary objective of this project was not simply to produce an NPV for three Netflix titles. It was to determine **how far defensible corporate finance analysis can go using public information—and where the evidence stops supporting a reliable investment conclusion.**

The model demonstrates that strong financial analysis requires both quantitative rigor and the judgment to recognize when a number should **not** be estimated.

