# Customer Churn Prediction

Academic internship project for the **IBM SkillsBuild Data Analytics with AI
Academic Internship Program**, conducted by **BharatCares** in association
with **AICTE**.

**Author:** Prashant Sharma

## Project description

Telecom companies lose a steady share of revenue to customer churn. This
project builds a supervised machine-learning pipeline that predicts whether a
customer is likely to cancel their service, based on their account details,
billing information, and the services they've subscribed to.

The notebook covers the full workflow:

1. Data cleaning (handling the blank `TotalCharges` values for brand-new
   accounts)
2. Exploratory data analysis (class balance, tenure/charge distributions,
   churn rate by contract type and internet service, correlation heatmap)
3. Preprocessing with a `scikit-learn` `ColumnTransformer` (imputation,
   scaling, one-hot encoding)
4. Training and comparing five classifiers — Logistic Regression, Decision
   Tree, Random Forest, Gradient Boosting, and an RBF-kernel SVM
5. Hyperparameter tuning of the best model (Gradient Boosting) via grid
   search
6. Evaluation (accuracy, precision, recall, F1, ROC-AUC, confusion matrix,
   ROC curves)
7. Feature importance analysis and business takeaways

### Results

The tuned Gradient Boosting model achieves **~80% accuracy** and
**ROC-AUC ≈ 0.85** on the held-out test set. The strongest predictors of
churn are contract type (month-to-month vs. annual), customer tenure, and
internet service type — full metrics and charts are in the notebook.

## Dataset

[Telco Customer Churn](https://www.kaggle.com/datasets/blastchar/telco-customer-churn)
— IBM's public sample telecom dataset, hosted on Kaggle by user *blastchar*.
7,043 customers, 21 columns (demographics, account info, subscribed
services, billing, and the `Churn` label). A local copy used for this
project is included at [`data/Telco-Customer-Churn.csv`](data/Telco-Customer-Churn.csv).

## Technologies used

- Python 3
- pandas, NumPy — data loading and cleaning
- scikit-learn — preprocessing pipeline, models, evaluation, grid search
- matplotlib, seaborn — visualization
- Jupyter Notebook

## Setup / run instructions

```bash
git clone https://github.com/ThatGUY12034/Customer-churn-prediction.git
cd Customer-churn-prediction

python3 -m venv .venv
source .venv/bin/activate        # Windows: .venv\Scripts\activate

pip install -r requirements.txt

jupyter notebook notebook/PrashantSharma_CustomerChurnPrediction.ipynb
```

Run all cells top to bottom to reproduce the EDA, model training, tuning,
and evaluation. The notebook expects the dataset at
`../data/Telco-Customer-Churn.csv` relative to itself (already included in
this repo).

## Repository structure

```
.
├── data/
│   └── Telco-Customer-Churn.csv
├── notebook/
│   └── PrashantSharma_CustomerChurnPrediction.ipynb
├── PrashantSharma_ProjectReport.docx
├── requirements.txt
└── README.md
```

## Key information

- **Program:** IBM SkillsBuild Data Analytics with AI — Academic Internship
  Program
- **Conducted by:** BharatCares, in association with AICTE
- **Problem type:** Binary classification (churn vs. no churn)
- **Best model:** Gradient Boosting Classifier (tuned via `GridSearchCV`)
