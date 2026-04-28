# DA5107 Submission Package

This folder contains a complete and report-ready deliverable.

## Main notebook
- `DA5107_Submission_Complete_EN.ipynb`

This notebook is designed to avoid the Plotly `fig.show()` rendering issue (`nbformat` errors) by using pre-generated static PNG charts and file-based outputs.

## Folder structure
- `scripts/`: all analysis code (Python + R)
- `data/`: key output tables and JSON summaries
- `figures/`: report charts (PNG)
- `raw/`: place the original `Assignment_data.csv` here for full rerun
- `outputs/`: reserved for additional generated files

## Quick start
1. Open `DA5107_Submission_Complete_EN.ipynb`.
2. Review sections 1-6 and visuals directly.
3. If needed, run optional cells to regenerate outputs.

## Full rerun from raw data (teacher reproducibility)
If your instructor wants to rerun all models from scratch:

1. Put the original raw file at `5107/raw/Assignment_data.csv` (or use any absolute path).
2. Install Python and R dependencies.
3. Run:

```bash
cd 5107
python3 scripts/run_full_pipeline.py --input_csv raw/Assignment_data.csv --clean_work_dir
```

The command refreshes:
- all model outputs in `data/`
- all charts in `figures/`
- intermediate outputs in `outputs/full_rerun/`

## Environment setup
Python:

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -U pip
pip install -r requirements.txt
```

R:

```r
install.packages("ggplot2")
```

## Executive Summary

This report evaluates the performance and future direction of the bank’s retail loan program from 
business, risk, portfolio, and strategy perspectives. Overall, the evidence suggests that the program should 
continue, but under a more selective and risk-disciplined model. 
The business review shows that the bank’s early expansion was too aggressive. From 2012 to 2015, loan 
count and loan amount grew at very high rates, while credit risk also increased. From 2016 to 2018, 
growth slowed and risk performance improved, indicating that the bank later corrected to a more 
sustainable pace. Pricing is directionally reasonable: higher-risk borrowers are charged higher interest 
rates, and both bad-loan rate and resolved charge-off rate rise clearly across grades. However, risk 
compensation becomes weaker in the riskiest segments, which means the current pricing strategy is not 
fully sufficient at the tail end of the portfolio. 
The credit assessment system is partly effective. The grading framework can rank risk well at portfolio 
level, but decision accuracy at borrower level still has room to improve. Among the tested models, 
Random Forest outperformed Logistic Regression and provided a better balance between bad-borrower 
capture and false positives. This makes it a more suitable model for credit screening, although it should 
still be combined with policy rules rather than used alone. Data quality is another important limitation. 
The dataset shows structural missingness, inconsistent field definitions, and some label conflicts. This 
means stronger data governance is necessary before the bank can fully scale model-driven decisioning. 
Under liquidity pressure, the portfolio should be managed using a controlled-max-return approach. 
Loans should be selected based on risk-adjusted return rather than volume, while PD caps and 
concentration limits should be applied to control tail risk. In customer management, not all churn should 
be treated as negative. A large share of exits comes from normal loan payoff, so the bank should focus on 
CLV-first retention, especially through pre-approved renewal and refinancing offers for good borrowers. 
Looking forward, the bank should follow a staged data analytics roadmap. It is currently between 
management reporting and predictive analytics integration. The next priorities are better data quality, 
stronger governance, and embedding analytics into approval, pricing, retention, and portfolio allocation 
workflows. Using Singapore as the reference market, the bank should expand selectively into 
renewal/refinancing products, repayment-linked savings, and basic financial management tools, 
rather than broad universal banking. LLM and Gen-AI should first be used in internal productivity and 
decision support, such as reporting, customer service support, and collections workflow, before being 
applied to more sensitive credit decisions. 
In summary, the bank has a viable lending business, but profitability and resilience will depend on slower 
growth, tighter risk control, better data governance, and more targeted product expansion.

