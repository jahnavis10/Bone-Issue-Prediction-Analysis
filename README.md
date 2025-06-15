## 🦴 Bone Issue Prediction – Osteoporosis / Osteoarthritis Classifier

Early detection of bone‐related conditions such as **Osteoporosis** and **Osteoarthritis** is crucial for preventing fractures and improving quality of life.  
This project walks through a full **data‑science pipeline**—from raw patient data to a deploy‑ready machine‑learning model—that predicts whether an individual has a bone disease based on physiological and lifestyle metrics.

---
## Project Motivation
* **Clinical Relevance:** Osteoporosis often remains undiagnosed until a fracture occurs. A data‑driven screening tool can prompt earlier diagnostics.  
* **Data Challenge:** The dataset mixes numerical labs (e.g., BMD, Vitamin D) and categorical lifestyle factors (Smoking, Exercise). This calls for thoughtful preprocessing and robust model selection.  
* **Learning Goals:** Showcase end‑to‑end ML workflow—EDA, feature engineering, baseline vs. tuned models, and clear evaluation—suitable for a data‑science resume.

Feature Highlights:
T‑score and BMD show the strongest negative correlation with disease severity.
Lifestyle factors (exercise frequency, smoking) shift risk distributions.
Interactive visuals (Seaborn/Matplotlib) illustrate distributions, outliers, and heat‑map correlations—see 01_eda.ipynb for details.

---

| Model                          | Accuracy | Precision | Recall | F1   |
| ------------------------------ | -------- | --------- | ------ | ---- |
| Logistic Regression (baseline) | ⚙️ 0.88  | 0.87      | 0.86   | 0.86 |
| KNN Algorithm                  | ⚙️ 0.80  | 0.89      | 0.85   | 0.87 |

Cross‑Validation: 5‑fold stratified CV to avoid class‑imbalance bias.
Hyper‑parameters: GridSearchCV on depth, estimators, class_weight.
Final Pick: Random Forest chosen for best trade‑off between interpretability and lift over baseline.

---

Key Findings
Age & T‑score dominate predictive power; combining them with lifestyle features boosts recall.
Simple models (LogReg) already achieve solid accuracy—suggesting strong signal in core diagnostic metrics.
Feature importance ranking (Gini gain) confirms clinical intuition: BMD‑related attributes top the list.
