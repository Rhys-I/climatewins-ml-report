# 🌦️ ClimateWins — Interim Machine Learning Report (Exercise 1.6)

**Author:** Rhys Ingalls  
**Program:** CareerFoundry — Machine Learning with Python  
**Date:** October 2025  

---

## 🎯 Project Overview
This project explores how machine learning can be used to understand and predict patterns in climate data. It’s part of the *ClimateWins* series from the CareerFoundry “Machine Learning with Python” specialization.  

The repository brings together Exercises **1.2 through 1.6**, combining data preparation, optimization, supervised learning, and final presentation into one complete project.  

👉 **Interactive Tableau Dashboard:**  
[View the live dashboard on Tableau Public →](https://public.tableau.com/app/profile/rhys.ingalls/viz/ClimateWins_Presentation/Dashboard1)

🎥 Watch the presentation video: [YouTube – ClimateWins Presentation](https://youtu.be/yTbekKT6FeU)

---

## 🧩 Objectives & Hypotheses
The overall objective is to identify relationships between weather features (temperature, humidity, pressure, etc.) and “pleasant weather” conditions, using regression, classification, and optimization.

**Proposed Hypotheses**
1. Household or regional energy-use patterns can be predicted using weather and occupancy features.  
2. Daily “pleasant weather” classification can be achieved using supervised algorithms such as Decision Trees or Neural Networks.  
3. Feature optimization will reveal temperature variance and humidity as primary contributors to prediction accuracy.  

---

## 🧠 Data Sources & Bias Considerations

**Datasets Used**
- European weather station data (temperature, humidity, pressure, wind speed).  
- Target variable: binary classification (`pleasant = 1`, `unpleasant = 0`).  

**Potential Biases & Mitigations**

| Bias Type | Description | Mitigation |
|------------|--------------|-------------|
| Sampling Bias | Uneven station coverage or time range | Stratified sampling and time-based validation |
| Sensor Bias | Instrument calibration drift | Outlier removal and sensor cross-checking |
| Concept Drift | Seasonal and behavioral changes | Recalibration with time-based CV |
| Label Noise | Subjective definitions of “pleasant” | Majority consensus or secondary reference data |

---

## ⚙️ Methods & Experiments

### **Exercise 1.2 — Data Preparation & Scaling**
- Standardized temperature and pressure features across all stations.  
- Serialized datasets using `pickle` for reusability.  

**Notebook:** `1.2_Weather_Dataset_Scaling_With_Pickle.ipynb`  
**Output:** Preprocessed CSV and pickle files.

---

### **Exercise 1.3 — Optimization and Gradient Descent**
- Implemented custom gradient descent for temperature modeling.  
- Learning rate (`α`) set to 0.01; convergence observed after ~70 iterations.  
- Demonstrated reduction of loss curve without oscillation.  

**Notebook:** `1.3_Gradient_Descent_for_Temperatures.ipynb`  
**Report:** `1.3 Optimization in Relation to Problem-Solving.pdf`

---

### **Exercise 1.4 — Supervised Learning Algorithms (Part 1)**
- Compared **K-Nearest Neighbors** and **Decision Trees**.  
- Decision Tree (depth=6) achieved perfect accuracy but overfitted.  
- KNN produced more balanced results and revealed data sensitivity.  

**Notebook:** `1.4_Supervised_Learning_Algorithms_Part_1.ipynb`  
**Report:** `1.4 Supervised Learning Algorithms Part 1.pdf`

---

### **Exercise 1.5 — Supervised Learning Algorithms (Part 2)**
- Implemented **Artificial Neural Networks (ANNs)** for classification.  
- Model `(5,5)` achieved 0.981 train and 0.975 test accuracy → best balance.  
- Deeper ANN `(20,10,5)` showed slight overfitting.  

**Notebook:** `1.5_Supervised_Learning_Algorithms_Part_2.ipynb`  
**Report:** `1.5 Supervised Learning Algorithms Part 2.pdf`

---

### **Exercise 1.6 — Presenting Machine Learning Results**
- Compiled final presentation deck and interactive Tableau dashboard.  
- Explained algorithm selection, data bias, and future recommendations.  
- Linked all results to CareerFoundry task rubric.  

**Presentation Deck:** `slides/ClimateWins_Presentation.pptx`  
**Dashboard:** [ClimateWins Tableau Dashboard](https://public.tableau.com/app/profile/rhys.ingalls/viz/ClimateWins_Presentation/Dashboard1)

---

## 📊 Model Performance Summary

| Model | Train Accuracy | Test Accuracy | Notes |
|--------|----------------|---------------|-------|
| KNN | 0.94 | 0.93 | Sensitive to k, varied by station |
| Decision Tree (depth 6) | 1.000 | 1.000 | Clear overfitting |
| ANN (5, 5) | **0.981** | **0.975** | Best generalization |
| ANN (10, 5) | 0.983 | 0.972 | Slight overfit |
| ANN (20, 10, 5) | 0.984 | 0.969 | Overfit increases with depth |

---

## 🧮 Repository Structure

```text
climatewins-ml-report/
│
├── data/
│   ├── Dataset_Weather_Prediction_Processed.csv
│   ├── Dataset_Answers_Weather_Prediction_Pleasant_Weather.csv
│   ├── ann_best_station_summary.csv
│   ├── dt_depth6_station_summary.csv
│   ├── model_runs_log.csv
│   └── station_accuracy_summary.csv
│
├── notebooks/
│   ├── 1.2_Weather_Dataset_Scaling_With_Pickle.ipynb
│   ├── 1.3_Gradient_Descent_for_Temperatures.ipynb
│   ├── 1.4_Supervised_Learning_Algorithms_Part_1.ipynb
│   └── 1.5_Supervised_Learning_Algorithms_Part_2.ipynb
│
├── reports/
│   ├── 1.2_ClimateWins_Ethics_Assessment.pdf
│   ├── 1.3_Optimization_in_Relation_to_Problem_Solving.pdf
│   ├── 1.4_Supervised_Learning_Algorithms_Part_1.pdf
│   ├── 1.5_Supervised_Learning_Algorithms_Part_2.pdf
│   └── interim_report.md
│
├── slides/
│   └── ClimateWins_Presentation.pptx
│
├── LICENSE  
├── requirements.txt  
└── README.md
