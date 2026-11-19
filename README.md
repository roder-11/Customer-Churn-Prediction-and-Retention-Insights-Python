# 📉 Customer Churn Prediction & Retention Insights

> **Which customers are about to leave, why, and what should the business do about it?**
> An end-to-end analysis of 3,333 subscribers: exploratory analysis, a baseline predictive model, and actionable retention recommendations.

![Python](https://img.shields.io/badge/Python-3.10+-blue) ![scikit-learn](https://img.shields.io/badge/scikit--learn-ML-orange) ![pandas](https://img.shields.io/badge/pandas-Analysis-green)
---

## 🎯 Business Problem

A subscription-based company is losing customers and wants to:
1. Understand **what drives churn**
2. **Identify at-risk customers** before they cancel
3. Define **targeted retention actions**

## 🔑 Key Findings

| # | Finding | Evidence |
|---|---------|----------|
| 1 | **~14.5% of customers churn** | 483 of 3,333 customers |
| 2 | **Contract non-renewal is the #1 churn signal** | 42% churn (137/323) vs 11% (346/3,010) for renewed contracts, about **4x higher** |
| 3 | **Churners call customer service more** | 2.2 vs 1.4 calls on average |
| 4 | **Churners pay higher monthly bills** | $59.2 vs $55.8 on average |
| 5 | **Tenure does not explain churn** | Average account age is nearly identical (~101 vs ~103 weeks) |

## 🤖 Model Performance (Baseline: Logistic Regression)

| Metric | Score |
|--------|-------|
| Accuracy | 0.866 |
| Precision | 0.596 |
| Recall | 0.196 |
| F1-score | 0.295 |

> ⚠️ **Accuracy is misleading here.** With only 14.5% churners, a model predicting "nobody leaves" already scores ~85%. The low **recall (0.20)** shows this baseline misses about **80% of departing customers**, which is the metric that matters most for retention. Improving it is the next step (see Roadmap).

## 💡 Business Recommendations

1. **Target non-renewed contracts first** with retention offers (discounts, commitment incentives): this is the highest-risk segment.
2. **Treat frequent customer-service callers as an early-warning signal**: proactive outreach and follow-up on unresolved issues.
3. **Review pricing for high-bill customers**: higher monthly charges are associated with higher churn.
4. **Upgrade the model before deploying it**, so it catches more real churners.

## 🛠️ Approach

1. **Load & explore** the data (structure, types, summary statistics)
2. **Clean & prepare**: drop index column, one-hot encode `ContractRenewal`
3. **EDA & visualization**: bar chart, histogram, box plot (churned vs retained)
4. **Modeling**: Logistic Regression (70/30 train-test split, `random_state=42`)
5. **Evaluation & reporting**: accuracy, precision, recall, F1 + business interpretation


```

## 📊 Dataset

3,333 customers, 11 features + target (`Churn`: 1 = left, 0 = stayed).

| Column | Description |
|--------|-------------|
| `Churn` | Target: customer left (1) or stayed (0) |
| `AccountWeeks` | Account age in weeks |
| `ContractRenewal` | Whether the contract was renewed (Yes/No) |
| `DataPlan` | Has a data plan (1/0) |
| `DataUsage` | Data usage |
| `CustServCalls` | Number of customer service calls |
| `DayMins` / `DayCalls` | Daytime minutes / calls |
| `MonthlyCharge` | Monthly bill |
| `OverageFee` | Overage fees |
| `RoamMins` | Roaming minutes |

```

## 🗺️ Roadmap

- [ ] Handle class imbalance (`class_weight='balanced'`)
- [ ] Tune the decision threshold to prioritize recall
- [ ] Compare Random Forest and Gradient Boosting
- [ ] Add ROC-AUC and precision-recall curves
- [ ] Add feature importance and a customer risk-scoring table
- [ ] Build a Power BI dashboard of churn drivers

## 👤 Author

**Awono Jean Rodrigue**: Business Intelligence & Data Analyst, transitioning to Data Engineering
📍 Douala, Cameroon

🔗 [LinkedIn]   · [GitHub](#)

