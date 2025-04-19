# Bank‑Fraud Analysis

> **Detect • Explain • Prevent**  
> Machine‑learning pipeline for spotting fraudulent banking transactions

---

## 📑 Project overview
Financial institutions process millions of transactions every day, and even a tiny fraud rate can translate into massive losses.  
This repository walks through the **full data‑science cycle**:

1. Load and explore the raw dataset (EDA).  
2. Clean data & engineer meaningful features.  
3. Tackle class imbalance, train and compare several models.  
4. Evaluate metrics and interpret top drivers of fraud.  
5. Export a ready‑to‑use pipeline that can be served in production.

Everything lives in a single, reproducible Jupyter notebook: `bank_fraud.ipynb`.

---

## 🗂️ Repository layout
```
│  README.md            # you’re reading it 🎉
│  bank_fraud.ipynb     # main notebook with code + commentary
├─ data/                # raw & processed datasets (empty in Git for GDPR)
├─ models/              # exported models / pipelines (.pkl)
└─ images/              # EDA plots, confusion matrices, SHAP charts
```
*Folders `data/`, `models/`, `images/` are created automatically on first run.*

---

## 🚀 Quick start
```bash
# 1 — clone the repo
git clone https://github.com/AlidarxD/bank_fraud_analysis.git
cd bank_fraud_analysis

# 2 — (optional) create a virtual env
python -m venv .venv && source .venv/bin/activate   # Windows: .venv\Scripts\activate

# 3 — install dependencies
pip install -r requirements.txt

# 4 — launch Jupyter
jupyter lab   # or jupyter notebook
```
Open `bank_fraud.ipynb` and run cells top → bottom.

---

## 🛠️ Tech stack
| Category              | Tools |
|-----------------------|-------|
| Core language         | **Python 3.11** |
| Data wrangling        | `pandas`, `numpy` |
| ML & imbalance        | `scikit‑learn`, `imbalanced‑learn` |
| Visualisation         | `matplotlib`, `seaborn` |
| Notebooks             | `Jupyter Lab` |

Full list → `requirements.txt`.

---

## 🔎 Dataset
The demo uses the public **Credit Card Fraud Detection** dataset (Kaggle).  
Each row represents a transaction; the target is column `Class` (1 = fraud, 0 = legit). All features were standardised via PCA, so the data are anonymised and GDPR‑safe.

> *Using a different dataset?*  Adjust column names in the *Data Loading* section of the notebook.

---

## 📊 Baseline vs tuned results
| Model                | ROC‑AUC | Recall (fraud) | Precision (fraud) |
|----------------------|:------:|:--------------:|:-----------------:|
| Logistic Regression  | 0.92 | 0.81 | 0.76 |
| Random Forest        | **0.97** | **0.90** | 0.88 |
| Gradient Boosting    | 0.96 | 0.88 | **0.89** |

**Random Forest** achieves the best recall/precision trade‑off and is selected as the final model.

---

## 📈 Next steps
* 🎯 **Hyperparameter search** with Optuna / Hyperopt.  
* 🧩 **Explainability** via SHAP or LIME for deeper insight.  
* 🌐 **FastAPI wrapper** → REST endpoint for real‑time scoring.  
* 📉 **Monitoring** — data‑drift & model‑decay reports in production.

PRs and feature requests are welcome!

---

## ⚠️ Disclaimer
This repository is educational. **Do not deploy the model to production as‑is** without additional legal checks, security hardening and live monitoring.

