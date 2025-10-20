# ClimateWins — Interim ML Report (Exercise 1.6)

**Prepared by:** Rhys Ingalls  
**Course:** CareerFoundry — Machine Learning with Python  
**Date:** October 2025  

---

## 🎯 Objective & Hypotheses
Evaluate machine learning models for classifying "pleasant" weather days across 15 European weather stations and identify overfitting behavior.

**Hypotheses**
1. A compact **ANN (two hidden layers)** will generalize best across stations.  
2. A **Decision Tree** will achieve perfect accuracy but exhibit overfitting.  
3. Differences in **temperature distributions** between stations will influence performance.

---

## 📊 Data Origin, Bias & Accuracy
- **Source:** Historical daily weather data from 15 European stations (multi-year CSVs).  
- **Label:** Pleasant (1) / Unpleasant (0) weather days.  
- **Coverage:** Stations include Basel, Gdańsk, Madrid, Belgrade, Budapest, Sonnblick, Valentia, etc.  
- **Bias Risks:** Unequal station data volume, imbalanced labels, seasonal differences.  
- **Accuracy Check:** Held-out test sets per station used for validation.  

---

## ⚙️ Optimization Recap — Gradient Descent (Exercise 1.3)
- **Parameters:** α = 0.01, 100 iterations, θ₀ = −5, θ₁ = −1.  
- **Result:** Smooth convergence for all stations (Basel, Gdańsk, Madrid).  
- **Behavior:** No oscillation or divergence; stable at ~iteration 60–80.  
- **Conclusion:** Same learning rate and iterations generalized across datasets — a strong base for scaling features and ML training.  

---

## 🤖 Supervised Learning — Model Results (Exercise 1.5)
**Algorithms Tested:** KNN, Decision Tree, and ANN (Multi-Layer Perceptron).

| Model | Train Acc | Test Acc | Notes |
|-------|------------|----------|-------|
| **KNN** | ~0.94 | ~0.93 | Slower; performance varied by station |
| **Decision Tree (depth=6)** | 1.000 | 1.000 | Perfect accuracy → clear overfitting |
| **ANN (5,5)** | **0.981** | **0.975** | Best generalization; stable results |
| **ANN (10,5)** | 0.983 | 0.972 | Slight overfit |
| **ANN (20,10,5)** | 0.984 | 0.969 | More overfit, small drop in test acc |

**Best Model:** ANN (5,5) — scaled data, high generalization (97–98% test accuracy).  
**Weakest Model:** Decision Tree — overfit, memorized training data.  
**Observation:** Station-level differences due to sample size and label imbalance.

---

## 📈 Tableau Dashboard Artifacts
Your Tableau visuals (shown in the PowerPoint deck) include:
- Temperature distribution by station (stacked histogram)
- Model performance by station (accuracy bars)
- Algorithm comparison (train vs test)
- Overfitting analysis (train–test gap)
- Confusion matrices for ANN and Decision Tree models  

---

## 🔍 Next Steps
- Perform k-fold cross-validation by station.  
- Address class imbalance with stratified sampling or threshold tuning.  
- Test ensemble methods (Random Forest, XGBoost).  
- Apply regularization to ANN (dropout, weight decay).  
- Evaluate ROC-AUC and calibration.  
- Document bias checks and set up drift monitoring.

---

## 🧩 Repository Layout
