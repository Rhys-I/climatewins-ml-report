# ClimateWins — Interim ML Report (Exercise 1.6)

This repository contains Rhys Ingalls' presentation and working files for **CareerFoundry — Machine Learning with Python, Exercise 1.6: Presenting Machine Learning Results**.

## 📦 Contents
- `slides/` — your presentation deck (PowerPoint, PDF, or Tableau export).
- `reports/` — interim report notes (Markdown) that mirror the deck.
- `src/` — optional helper scripts (data prep, charts).
- `notebooks/` — optional Jupyter exploration.
- `data/` — any non-sensitive sample data used to illustrate methods (avoid PII).

## 🎯 Presentation Checklist (matches rubric)
- [ ] Cover slide — title, date, your name
- [ ] Objective from project brief + **at least three hypotheses**
- [ ] Data origin, **potential biases**, and accuracy/limits
- [ ] How **optimization** informed feature selection
- [ ] **Supervised learning** chosen and why (algorithms + rationale)
- [ ] Summary: hypotheses + methods, **next steps** and future analysis
- [ ] Exit slide — “Questions / Thank you” + contact
- [ ] Repo pushed to GitHub with slides and supporting files

---

## 🧪 Draft Hypotheses (edit me)
1. **Household energy-use segments** (low/medium/high) can be predicted from weather + occupancy features using classification.
2. **Daily energy demand** (kWh) can be forecast at the neighborhood level from seasonality + temperature using regression.
3. **Outlier detection** can flag anomalous meters (possible sensor faults or leaks) via clustering-based anomaly scores.

> Replace these with your exact ClimateWins hypotheses if you have different ones.

---

## 🧠 Bias & Data Accuracy Notes (starter)
- **Sampling**: geographic region, season coverage, and socioeconomics may be uneven.
- **Sensor bias**: meter calibration drift; missing intervals; smartphone-only data underrepresents older users.
- **Concept drift**: behavior changes post-policy incentives; distribution shift across years.
- **Label noise**: self-reported outcomes vs. measured signals.

Mitigations: holdout periods by time/location, calibration checks, robust metrics (MAE + prediction intervals), fairness audit slices.

---

## ⚙️ Methods (starter mapping)
- **Optimization**: feature selection via regularization (L1/L2), stepwise AIC/BIC, or randomized search over engineered weather lags.
- **Supervised**: 
  - Regression: Linear/Elastic Net, Random Forest Regressor, Gradient Boosting.
  - Classification: Logistic Regression, Random Forest/Gradient Boosting; evaluate ROC AUC / PR AUC.
- **Unsupervised (context)**: KMeans/DBSCAN for customer segments or anomaly detection.

Evaluation: time-based CV, nested CV for hyperparameters; report MAE/MAPE (regression) and ROC AUC/F1 (classification).

---

## 🚀 How to Use
1. Put your deck file into `slides/` (e.g., `climatewins_ex1_6.pptx`).
2. Capture interim notes in `reports/interim_report.md`.
3. Optionally add notebooks or scripts you referenced.
4. Commit and push to GitHub (see quickstart below).

---

## 🟦 GitHub Quickstart
```bash
# in a terminal
git clone <YOUR_EMPTY_REPO_URL>.git climatewins-ml-report
cd climatewins-ml-report

# copy these files into the folder if you downloaded a ZIP
# (or unzip this package directly into the cloned folder)

git add .
git commit -m "Add Exercise 1.6 ClimateWins interim report and deck scaffold"
git push origin main
```
If you haven’t created the remote yet, see the **Commands to Create a New Repo** section below.

---

## 🔬 Repro Environment (optional)
- Python ≥ 3.10
- See `requirements.txt` for minimal libs

```bash
python -m venv .venv
source .venv/bin/activate  # Windows: .venv\Scripts\activate
pip install -r requirements.txt
```

---

## 📝 License
MIT — see `LICENSE`.

---

## 🛠 Commands to Create a New Repo (GitHub)
1. Create a **new empty repository** on GitHub named `climatewins-ml-report` (no README, no .gitignore).
2. Initialize locally and push:
```bash
mkdir climatewins-ml-report && cd climatewins-ml-report
git init -b main
echo "# ClimateWins — Interim ML Report" > README.md
git add .
git commit -m "Initial commit"
git remote add origin https://github.com/<YOUR_USERNAME>/climatewins-ml-report.git
git push -u origin main
```
3. Add the rest of these scaffold files, commit, and push.
```bash
git add .
git commit -m "Add scaffold: slides/, reports/, src/, notebooks/"
git push
```

---

## ✅ Submission Notes
- Upload your **slides** (and optional recording link) to the course portal.
- Ensure your **GitHub repo** is public or shared with your mentor.
- Include the repo link in your submission message.
