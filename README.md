# Ultimate Technologies Inc. — Data Science Take-Home Challenge

A three-part data science challenge adapted from a real interview process at a major
ride-sharing company. The analysis covers demand forecasting, A/B experiment design,
and predictive modeling for rider retention.

---

## Project Overview

| Part | Topic | Methods |
|------|-------|---------|
| 1 | Exploratory Data Analysis — login demand patterns | Time series aggregation, heatmaps, rolling averages |
| 2 | Experiment & Metrics Design — cross-city driver incentive | A/B test design, statistical testing, causal reasoning |
| 3 | Predictive Modeling — 6-month rider retention | Random Forest, cross-validation, feature importance |

---

## Key Results

**Part 1 — Login Demand**
- Aggregated 93,142 login timestamps into 15-minute bins across a 103-day window
- Identified a bimodal daily cycle (morning peak ~8–9 AM, evening peak ~9–10 PM)
- Weekend demand is higher than weekday demand, driven by late-night activity (midnight–5 AM Saturday/Sunday)
- Flagged epoch-year timestamps (1970) as a data quality anomaly — relative time patterns remain valid

**Part 2 — Experiment Design**
- Proposed **cross-city driver rate** (% of drivers completing trips in both cities per week) as the primary success metric
- Designed a 4-week randomized controlled trial with driver-level randomization, stratified by home city
- Outlined two-proportion z-test for significance, weekly trend checks for novelty effects, and subgroup analyses

**Part 3 — Rider Retention Model**
- 37.6% of the 50,000-user January 2014 cohort were retained at month 6
- Compared Logistic Regression, Gradient Boosting (CV AUC: 0.8551), and Random Forest (CV AUC: 0.8463)
- Selected **Random Forest** for its near-equivalent performance, lower variance, and interpretability
- **Test ROC-AUC: 0.85** | Accuracy: 78%
- Top predictors: driver rating of rider, city of signup, surge usage pattern, weekday trip share

---

## Repository Structure

```
├── ultimate_challenge_solution.ipynb   # Full analysis notebook (Parts 1–3)
├── logins.json                         # Login timestamp data (Part 1)
└── ultimate_data_challenge.json        # Rider cohort data (Part 3)
```

## Setup & Usage

**Requirements**
```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```

**Run the notebook**
```bash
jupyter notebook ultimate_challenge_solution.ipynb
```
Then run all cells (Kernel → Restart & Run All). All figures are saved as `.png` files in the working directory.

---

## Tools & Libraries

`Python` · `pandas` · `NumPy` · `scikit-learn` · `Matplotlib` · `Seaborn`
