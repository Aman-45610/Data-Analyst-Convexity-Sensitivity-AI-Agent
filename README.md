# Data Analyst Convexity Sensitivity AI Agent

## Project Overview

**Project:** Data Analyst Convexity Sensitivity AI Agent  
**Domain:** Fixed Income / Bond Portfolio Risk Analytics  
**Objective:** Build an integrated risk analytics and AI-agent solution that measures bond portfolio sensitivity to interest-rate movements using duration, convexity, DV01, key-rate duration, yield-curve scenarios, Monte Carlo simulation, and machine-learning models.

The project combines Python, R, Excel, and Power BI into a practical training and risk-analysis platform called **Bond Risk Lab**.

---

## 1. Project Objectives

The project is designed to:

- Analyze bond portfolio duration and convexity sensitivity.
- Calculate Modified Duration, Convexity, DV01, and Key Rate Duration.
- Measure portfolio P&L under interest-rate shocks.
- Analyze parallel, steepening, flattening, and butterfly yield-curve scenarios.
- Estimate Monte Carlo VaR and CVaR.
- Compare Random Forest, XGBoost, and Neural Network models.
- Identify important risk drivers using machine-learning feature importance.
- Provide a natural-language AI Risk Agent for portfolio risk questions.
- Build an Excel-based Bond Risk Lab simulation.
- Build an interactive Power BI risk dashboard.
- Implement the core risk analysis independently in R.

---

## 2. Project Architecture

Data Sources
    |
    v
Portfolio + Yield Curve + Monte Carlo Data
    |
    v
Python Risk Engine
    |
    +--> Duration / Convexity / DV01
    |
    +--> Key Rate Duration
    |
    +--> Yield Curve Scenarios
    |
    +--> Monte Carlo Risk
    |
    +--> Machine Learning
    |
    v
AI Risk Agent
    |
    +--> Excel Bond Risk Lab
    |
    +--> Power BI Dashboard
    |
    +--> R Risk Analysis
    |
    v
Final Risk & Training Platform

---

## 3. Dataset Summary

### Bond Portfolio

- Records: 300 bonds
- Market Value: INR 32,059,345.97
- Portfolio Modified Duration: 4.203131
- Portfolio Convexity: 44.061379
- Portfolio DV01: INR 8,948.25

### Historical Yield Curve

- Records: 264
- Tenors: 3M, 6M, 1Y, 2Y, 3Y, 5Y, 7Y, 10Y, 15Y, 20Y, 30Y
- Latest curve date used: 2024-10-30

### Monte Carlo Scenarios

- Scenarios: 1,000
- Minimum P&L: INR -3,399,503.91
- Maximum P&L: INR 5,948,564.10
- Mean P&L: INR 84,166.30
- VaR 95%: INR 1,976,671.43
- CVaR 95%: INR 2,377,153.69

---

## 4. Core Risk Formula

The project uses the duration-convexity approximation:

ΔP/P ≈ -D × Δy + 0.5 × C × (Δy)^2

Where:

- D = Modified Duration
- C = Convexity
- Δy = Yield change in decimal form

Duration estimates the first-order price sensitivity to yield changes, while convexity captures the second-order curvature effect.

---

## 5. Portfolio Risk Results

### Stress Testing

| Yield Shock | Total P&L (INR) |
|---:|---:|
| -200 bps | 2,977,508.3 |
| -100 bps | 1,418,125.2 |
| -50 bps | 691,405.4 |
| +50 bps | -656,090.9 |
| +100 bps | -1,276,867.3 |
| +200 bps | -2,412,476.7 |

The results demonstrate the portfolio's sensitivity to changes in interest rates, with convexity providing a second-order adjustment to the duration-only estimate.

---

## 6. Key Rate Duration

| Key Rate Bucket | KRD |
|---|---:|
| 0-1Y | 0.04525714 |
| 1-2Y | 0.21140688 |
| 2-3Y | 0.43352180 |
| 3-5Y | 0.43290915 |
| 5-7Y | 0.38795516 |
| 7-10Y | 0.45992140 |
| 10-15Y | 0.55036366 |
| 15-20Y | 0.98047249 |
| 20Y+ | 0.70132309 |

---

## 7. Yield Curve Scenario Analysis

The project evaluates five predefined curve scenarios.

| Scenario | P&L (INR) |
|---|---:|
| Parallel +50 bps | -673,748.1 |
| Parallel -50 bps | 673,748.1 |
| Steepening | -480,375.8 |
| Flattening | -215,337.0 |
| Butterfly | -507,050.9 |

The scenario engine applies the predefined key-rate shocks to the corresponding KRD buckets.

---

## 8. Monte Carlo Risk Analysis

The supplied Monte Carlo scenario dataset contains 1,000 simulated P&L observations.

### Results

- Minimum P&L: INR -3,399,503.91
- Maximum P&L: INR 5,948,564.10
- Mean P&L: INR 84,166.30
- Median P&L: INR 62,955.29
- Standard Deviation: INR 1,293,117.19
- VaR 95%: INR 1,976,671.43
- CVaR 95%: INR 2,377,153.69

VaR represents the estimated loss threshold at the 95% confidence level, while CVaR represents the average loss in the worst 5% tail of the supplied simulation.

---

## 9. Machine Learning

Three models were compared for the bond-risk prediction task:

1. Random Forest
2. XGBoost
3. Neural Network

### Model Results

| Model | MAE | RMSE | R² |
|---|---:|---:|---:|
| Random Forest | 0.2917564 | 0.6170306 | 0.9729033 |
| XGBoost | 0.2278874 | 0.4550983 | 0.9852594 |
| Neural Network | 0.2472629 | 0.4197878 | 0.9874581 |

### XGBoost Feature Importance

| Feature | Importance |
|---|---:|
| CouponRate | 0.002925956 |
| YearsToMaturity | 0.063755450 |
| YieldToMaturity | 0.007741395 |
| ModifiedDuration | 0.324682668 |
| Convexity | 0.600894530 |

The model results show that convexity and modified duration are major features in the supplied ML analysis.

---

## 10. AI Risk Agent

The AI Risk Agent integrates the project's major risk outputs into a natural-language interface.

It can answer questions involving:

- Portfolio market value
- Modified duration
- Convexity
- DV01
- Stress-test P&L
- Yield-curve scenarios
- Key-rate duration
- Monte Carlo VaR
- Monte Carlo CVaR
- ML model performance
- ML feature importance

### Example Queries

- What happens if yields rise by 100 bps?
- What is the portfolio DV01?
- Which key-rate bucket has the largest KRD?
- What is the 95% VaR?
- What is the CVaR?
- What is the P&L under a steepening scenario?
- Which ML model has the reported highest R²?
- Which features are most important in the XGBoost model?

---

## 11. Power BI Dashboard

The Power BI implementation contains five pages:

### Page 1 — Executive Risk Dashboard
Portfolio-level risk metrics and stress-test information.

### Page 2 — Yield Curve & Scenarios
Latest yield curve, KRD, and predefined curve-scenario analysis.

### Page 3 — Monte Carlo Risk
Monte Carlo P&L distribution and VaR/CVaR metrics.

### Page 4 — Machine Learning
Model comparison and feature-importance analysis.

### Page 5 — Bond Risk Lab
Interactive training and risk-simulation content.

Key Power BI measures include:

- Portfolio Market Value
- Portfolio Modified Duration
- Portfolio Convexity
- Portfolio DV01
- VaR 95%
- CVaR 95%
- Mean P&L
- Minimum P&L
- Maximum P&L

---

## 12. Excel Bond Risk Lab

The Excel workbook provides a training-oriented fixed-income risk environment.

### Six Levels

1. Rate Shock Rookie
2. Convexity Explorer
3. Curve Strategist
4. Monte Carlo Trader
5. ML Risk Analyst
6. Crisis Risk Manager

Total scoring system: **1,000 points**

The levels progressively cover interest-rate shocks, convexity, yield-curve movements, Monte Carlo risk, machine learning, and crisis scenarios.

---

## 13. R Implementation

The R implementation independently reproduces the core portfolio-risk workflow.

The completed R analysis calculates:

- Portfolio market value
- Modified duration
- Convexity
- DV01
- Stress-test P&L
- Key-rate duration
- Latest yield curve
- Yield-curve scenario P&L
- Monte Carlo VaR/CVaR
- ML model comparison
- ML feature importance
- Combined risk report

The final R execution completed successfully with exit code 0.

Generated R outputs are stored in:

outputs/r_results/

---

## 14. Project Structure

Convexity_Sensitivity_AI_Agent/

    data/
        bond_portfolio_data.csv
        yield_curve_history.csv
        monte_carlo_scenarios.csv

    python/
        01_data_validation.py
        02_risk_engine.py
        03_yield_curve.py
        04_monte_carlo.py
        05_machine_learning.py
        06_ai_agent.py
        07_prepare_dashboard_data.py

    r/
        risk_analysis.R

    powerbi/
        dashboard.pbix

    excel/
        Bond_Risk_Lab.xlsx

    outputs/
        portfolio_summary.csv
        krd_analysis.csv
        stress_test_results.csv
        latest_yield_curve.csv
        curve_scenario_results.csv
        monte_carlo_summary.csv
        ml_model_comparison.csv
        ml_feature_importance.csv
        r_results/

    README.md

---

## 15. Technology Stack

### Programming
- Python
- R

### Data Analysis
- Pandas
- NumPy
- CSV-based financial datasets

### Machine Learning
- Random Forest
- XGBoost
- Neural Network

### Visualization / BI
- Microsoft Power BI
- Microsoft Excel

### Risk Analytics
- Duration
- Convexity
- DV01
- Key Rate Duration
- Yield Curve Analysis
- Monte Carlo Simulation
- VaR
- CVaR

### AI
- Natural-language AI Risk Agent

---

## 16. Project Workflow

The completed workflow is:

1. Validate financial datasets.
2. Calculate portfolio duration, convexity, and DV01.
3. Calculate key-rate duration.
4. Perform interest-rate stress testing.
5. Analyze yield-curve scenarios.
6. Perform Monte Carlo risk analysis.
7. Train and compare ML models.
8. Analyze ML feature importance.
9. Integrate outputs into the AI Risk Agent.
10. Prepare dashboard datasets.
11. Build the Excel Bond Risk Lab.
12. Build the Power BI dashboard.
13. Reproduce the analysis in R.
14. Generate final project outputs and documentation.

---

## 17. Final Project Status

### Completed Components

- [x] Data validation
- [x] Python risk engine
- [x] Duration and convexity analysis
- [x] DV01
- [x] Key Rate Duration
- [x] Yield curve analytics
- [x] Curve scenarios
- [x] Monte Carlo analysis
- [x] VaR / CVaR
- [x] Random Forest
- [x] XGBoost
- [x] Neural Network
- [x] ML feature importance
- [x] AI Risk Agent
- [x] Dashboard data preparation
- [x] Excel Bond Risk Lab
- [x] Power BI dashboard
- [x] R implementation
- [x] R output generation
- [x] Final documentation

---

## 18. Conclusion

The project delivers an integrated fixed-income risk analytics platform that combines traditional bond-risk measures with scenario analysis, Monte Carlo simulation, machine learning, business intelligence, and an AI-driven natural-language interface.

The completed solution provides a unified workflow for understanding how a bond portfolio responds to interest-rate shocks, yield-curve movements, and simulated market scenarios while also providing an interactive environment for learning fixed-income risk analysis.
