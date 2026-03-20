# AD Campaign Performance Prediction

## Overview
A machine learning project to predict the number of orders generated
from product marketing campaigns. Built as part of the BIA® Research
Internship at First Quadrant Labs.

Accurate campaign performance prediction enables marketing teams to
optimize resource allocation, reduce wasted spend, and maximize ROI
before campaigns go live.

## Dataset
- **Size:** 731 rows × 11 features
- **Target variable:** `orders` — number of orders generated
- **Features:** campaign type, level, resource amount, email rate,
  price, discount rate, labor hours, campaign fee

## Methodology
1. Data Loading & Inspection
2. Data Cleaning & Type Conversion
3. Feature Engineering — 6 new business-driven variables
4. Model Preparation — encoding, train/test split, scaling
5. Model Training & Evaluation — 5 models compared
6. Hyperparameter Tuning — XGBoost optimization
7. Regularization Analysis — Ridge & Lasso
8. Visualization & Business Insights
9. Power BI Dashboard

## Feature Engineering
| Feature | Formula | Business Meaning |
|---|---|---|
| `effective_price` | price × (1 - discount_rate) | Actual selling price |
| `ROI` | orders / campaign_fee | Return per ₹ spent |
| `cost_per_order` | campaign_fee / orders | Acquisition cost |
| `budget_per_hour` | resource_amount / hour_resources | Resource efficiency |
| `discount_impact` | price × discount_rate | Revenue lost to discount |
| `revenue_estimate` | orders × effective_price | Projected revenue |

## Model Results
| Model | R² | MAE | RMSE |
|---|---|---|---|
| **Linear Regression** | **0.999** | **27.75** | **55.26** |
| Gradient Boosting | 0.997 | 77.62 | 100.83 |
| Random Forest | 0.997 | 72.79 | 110.71 |
| XGBoost (tuned) | — | — | — |
| Ridge Regression | ~0.999 | — | — |
| Lasso Regression | ~0.999 | — | — |

**Selected Model:** Linear Regression — highest R², lowest error,
no overfitting detected.

## Key Business Insights
- Campaign fee and resource allocation are the strongest drivers of orders
- Budget-per-hour efficiency outperforms raw spend as a predictor
- Discount rate alone does not guarantee higher orders —
  effective price matters more
- ROI-optimized campaigns consistently outperform high-budget,
  low-efficiency ones

## Tech Stack
Python • Pandas • NumPy • Scikit-learn • XGBoost •
Matplotlib • Seaborn • Power BI • Jupyter Notebooks

## Deliverables
- `Notebookipynb.ipynb` — Full analysis pipeline
- `Presentation.pptx` — Executive summary
- `Product_Ad_Campaign_Performance.pbix` — Power BI dashboard
- Prediction CSVs for all models

## About
Part of a 6-month BIA® Research Internship at First Quadrant Labs.
Project 1 of 6 — focused on marketing analytics and campaign optimization.
