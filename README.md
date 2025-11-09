# DA5401-Assignment-8 — Ensemble Learning for Complex Regression Modeling on Bike Share Data

**Name:** Aryan Prasad  
**Roll No:** DA25M007  

---

## 🧠 Overview
This assignment applies and compares three ensemble learning techniques — **Bagging**, **Boosting**, and **Stacking** — for predicting hourly bike rental counts (`cnt`) from the **UCI Bike Sharing Demand Dataset**.  
The objective is to analyze how each method tackles the **bias–variance trade-off** and improves predictive accuracy over single models using **Root Mean Squared Error (RMSE)** as the evaluation metric.

---

## 🚲 Dataset Description
**Source:** UCI Machine Learning Repository  
**Samples:** 17 379 (hourly) **Target:** `cnt` (Total rentals)  

**Features**
- **Time-based:** `yr`, `mnth`, `hr`, `weekday`, `holiday`, `workingday`  
- **Weather-related:** `temp`, `atemp`, `hum`, `windspeed`  
- **Categorical:** `season`, `weathersit`  

**Dropped Columns:** `instant`, `dteday`, `casual`, `registered` (redundant / leakage)

---

## ⚙️ Workflow Summary
| Part | Focus | Key Methods |
|:----:|:------|:------------|
| A | Preprocessing & Baseline | Linear Regression and Decision Tree (max_depth = 6) |
| B | Ensemble Methods | Bagging (variance reduction) & Gradient Boosting (bias reduction) |
| C | Stacking | KNN + Bagging + GB with Ridge meta-learner |
| D | Final Analysis | RMSE comparison & bias–variance interpretation |

---

## 📊 Results
| Model | RMSE |
|:--------------------------------------------|:-----------:|
| Baseline (best of DT / Linear Regression) | 133.84 |
| Bagging Regressor | 155.48 |
| Gradient Boosting Regressor | 122.45 |
| **Stacking Regressor (KNN + Bagging + GB → Ridge)** | **114.17** |

**🏆 Best Model:** Stacking Regressor  

---

## 🔍 Insights
- **Baseline Models:** Linear Regression > Decision Tree → baseline RMSE 133.84.  
- **Bagging:** Reduced variance but minor accuracy gain.  
- **Boosting:** Corrected bias → major improvement (RMSE 122.45).  
- **Stacking:** Blended diverse models via Ridge meta-learner → best generalization (RMSE 114.17).  

---

## ⚖️ Bias–Variance Summary
| Model | Bias | Variance | Comment |
|:------|:-----:|:---------:|:--------|
| Decision Tree | Low | High | Overfits |
| Bagging | ≈ Low | ↓ Variance | Stabilizes predictions |
| Boosting | ↓ Bias | Slight ↑ Variance | Captures non-linearity |
| Stacking | ↓ Bias | ↓ Variance | Best balance |

---

## 📈 Visual Highlights
- **Correlation Heatmap** — Feature relationships with `cnt`.  
- **Hourly Trend Plot** — Morning & evening rental peaks.  
- **Distribution Plot** — Right-skewed rental frequency.  
- **Actual vs Predicted** — Side-by-side for Bagging & Boosting.  
- **RMSE Trend Plot** — Shows steady improvement to Stacking.  
- **Error Distribution** — Stacking errors narrower and centered around 0.  

---

## 🧠 Key Interpretation
- **Bagging** ↓ variance. **Boosting** ↓ bias. **Stacking** balances both.  
- **Ridge Meta-Learner** adds L2 regularization to avoid overfitting.  
- Ensemble methods show clear superiority over single models in handling non-linearity and feature interaction.

---

## ✅ Final Conclusion
**Stacking Regressor achieved the lowest RMSE (114.17)** — ≈ 15 % improvement over the baseline.  
By combining KNN, Bagging, and Gradient Boosting with a Ridge meta-learner, it achieved optimal bias–variance trade-off and the most accurate bike-demand predictions.

---

