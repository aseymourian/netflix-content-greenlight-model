Netflix Content Greenlight Financial Model

A capital budgeting model applying corporate finance methodology (WACC, NPV, payback period, sensitivity analysis) to three real Netflix content investment decisions evaluating whether the numbers supported the calls Netflix made.
Titles analyzed:
•	Red Notice (2021) original content greenlight, backtested against real performance
•	Extraction → Extraction 2 franchise continuation decision, validated against actual sequel outcome
•	The Super Mario Bros. Movie licensing/streaming-rights acquisition, a structurally different decision type from the other two
 
Key Findings

•	WACC = 10.79%, built from scratch using Netflix's FY2025 10-K and Q2 2026 10-Q: CAPM-derived cost of equity (11.11%), a par-value-weighted cost of debt across all 12 outstanding note tranches (4.76% pre-tax / 3.91% after-tax), and market-value capital weights (95.6% equity / 4.4% debt)
•	Beta (1.526) was independently computed via a 5-year OLS regression of NFLX monthly returns against the S&P 500 and cross-validated against vendor-cited figures (Yahoo Finance: 1.49–1.71)
•	A comps-based forecast for Red Notice was tested and rejected. Regressing hours-viewed against production budget across 8 comparable Netflix originals returned R² = 0.031, p = 0.677 statistically indistinguishable from noise. Rather than force a fabricated point estimate, the model pivoted to evaluating each title as a backtest against real, sourced outcome data instead of a blind forecast.
•	Red Notice and Extraction both show negative NPV within Netflix's disclosed 91-day measurement window but the model argues this is a conservative floor, not a lifetime estimate, and shows why (see Limitations).
•	Mario's licensing cost is not publicly disclosed anywhere for this title or any comparable one under Netflix's Universal/Illumination/DreamWorks output deal so NPV/payback couldn't be calculated. The model documents why transparently rather than guessing at a number.
 
Methodology

Discount rate: Netflix's company-wide WACC is applied uniformly across all three titles, rather than a project-specific risk premium. Single-title outcome risk (will this movie hit or flop) is predominantly idiosyncratic diversifiable across Netflix's full content slate and CAPM theory says idiosyncratic risk shouldn't be priced into the discount rate. That uncertainty is instead captured through sensitivity analysis on the cash flow side.
Revenue attribution: Hours viewed → dollars, via a Value per Hour rate derived from Netflix's own disclosed financials (global blended ARPU ÷ average hours watched per member per month). This avoids the far shakier alternative of estimating subscriber acquisition/retention per title, which Netflix doesn't disclose and no reliable public methodology exists for.
Validation, not just calculation: Value per Hour was cross-checked against an independent figure content amortization expense (10-Q) divided by platform-wide hours viewed confirming revenue-per-hour exceeds cost-per-hour by a directionally sensible ~2.65x.
 
A Real Data-Methodology Finding

Netflix changed its public engagement-tracking standard in November 2021, from "households reached in 28 days" to "hours viewed in 91 days." Titles released before that date simply don't exist in the current metric not withheld, never measured that way. This creates a hard structural ceiling on how large a same-methodology comp set can get from public data alone, and is documented explicitly in the model's README tab rather than papered over by blending incompatible metrics.
The Super Mario Bros. Movie's own engagement data makes the deeper limitation concrete: its first-8-week hours-viewed figure (6.5M) is roughly 30x smaller than its calendar-year-2024 figure alone (195.3M, US-only) direct evidence that a 91-day snapshot substantially understates a title's true lifetime value.
 
What's in This Repository

File	Contents
01_cleaning_data_finance.xlsx	Full workbook: Assumptions, Metrics (WACC build), beta regression source data, three title-decision tabs, Sensitivity analysis, Go/No-Go Summary, and a fully sourced README tab
Workbook tabs:
•	Assumptions every input, long-format with source, confidence tier (High/Medium/Low), and notes
•	Metrics the full WACC build: beta regression output, CAPM, cost of debt, capital structure weights
•	Red Notice / Extraction / Mario NPV, payback period, and cash flow analysis per title
•	Sensitivity two-variable sensitivity grids (Value per Hour × Discount Rate for Red Notice/Extraction; Value per Hour × measurement window for Mario)
•	Go or No Go Summary final recommendation per title, with explicit rationale
•	README full sourcing documentation, confidence-tier definitions, and methodology limitations
 
Skills Demonstrated

Corporate finance (WACC, CAPM, NPV, payback period) · statistical regression and diagnostics (OLS, R², p-values, confidence/prediction intervals) · data sourcing and confidence-tiering across SEC filings, primary company disclosures, and secondary press · Excel formula-building (SLOPE, LINEST, SUMPRODUCT) · honest reporting of a null result rather than a forced conclusion
 
A Note on Data Limitations

This model relies exclusively on public data sources, since internal Netflix engagement and financial systems aren't accessible externally. A production analyst in this seat would have access to richer internal data granular subscriber attribution, unredacted budgets, cross-era-consistent engagement tracking that would resolve several of the constraints documented here. The underlying analytical approach (comps-based forecasting, methodology-consistency checks, defensible confidence tiering) mirrors how that internal data would be used; the full reasoning behind every judgment call is documented in the workbook's README tab.
