# Employee Attrition Prediction Model

**Author:** Oluwatobi (Tobi) Abanishe  
**Tools:** Python, Scikit-learn, Power BI  
**Dataset:** IBM HR Analytics Employee Attrition Dataset (Kaggle)  
**Type:** Predictive Analytics · Classification

---

## What This Project Does

This project builds a logistic regression model that predicts which employees are most likely to leave an organisation voluntarily. The goal is not just to predict attrition — it is to explain *why* it happens, in language that an HR Business Partner can take into a conversation with a business leader.

The model is trained on IBM's publicly available HR Analytics dataset, which covers 1,470 employees across 35 variables including job role, satisfaction scores, overtime, tenure, and compensation. The final output is a ranked list of attrition drivers with business recommendations attached.

---

## The Business Question

> *Which employees are at risk of leaving, and what can the business actually do about it?*

Most attrition reports tell you what already happened. This model tells you what is likely to happen next — and which lever to pull first.

---

## Dataset

| Field | Detail |
|---|---|
| Source | [IBM HR Analytics Employee Attrition Dataset](https://www.kaggle.com/datasets/pavansubhasht/ibm-hr-analytics-attrition-dataset) |
| Publisher | IBM Watson Analytics (via Kaggle) |
| Rows | 1,470 employees |
| Columns | 35 variables |
| Target variable | `Attrition` (Yes / No) |
| Licence | Open Database Licence (ODbL) |

To run this project, download `WA_Fn-UseC_-HR-Employee-Attrition.csv` from the Kaggle link above and place it in the `/data` folder.

---

## Key Findings

1. **Overtime is the single strongest predictor.** Employees who work overtime are **2.3x more likely to leave** than those who do not, regardless of pay level. This means paying someone more while keeping them on permanent overtime is not a retention strategy.

2. **Years in current role matters more than total tenure.** Employees stuck in the same role for 3 or more years without a promotion show significantly elevated risk. Tenure in the company alone is not protective.

3. **Low job satisfaction accelerates departure but does not cause it alone.** Satisfaction scores below 2 (out of 4) combined with overtime created the highest-risk employee profile in the dataset.

4. **Monthly income has a threshold effect.** Below approximately $3,500/month, income is a strong predictor of attrition. Above that threshold, its influence drops sharply. Paying above the threshold buys stability; paying well above it does not buy proportionally more loyalty.

5. **Sales Representatives and Lab Technicians had the highest attrition rates by job role**, at 39% and 24% respectively. These roles also had the highest overtime exposure, suggesting structural workload issues rather than individual dissatisfaction.

---

## Model Performance

| Metric | Score |
|---|---|
| Accuracy | 88% |
| Precision (Attrition = Yes) | 81% |
| Recall (Attrition = Yes) | 74% |
| ROC-AUC | 0.86 |

The model was validated using a stratified 80/20 train-test split with cross-validation to account for class imbalance (only ~16% of employees in the dataset actually left).

---

## Project Structure

```
attrition-model/
│
├── data/
│   └── WA_Fn-UseC_-HR-Employee-Attrition.csv   ← download from Kaggle
│
├── notebooks/
│   └── attrition_model.ipynb                    ← full analysis notebook
│
├── requirements.txt                             ← Python dependencies
└── README.md
```

---

## How to Run

```bash
# 1. Clone the repo
git clone https://github.com/TobiAbanishe/attrition-model.git
cd attrition-model

# 2. Install dependencies
pip install -r requirements.txt

# 3. Add the dataset
# Download from Kaggle and place in /data folder

# 4. Open the notebook
jupyter notebook notebooks/attrition_model.ipynb
```

---

## Business Recommendations

Based on the model outputs, three actions have the highest expected impact on reducing voluntary attrition:

**1. Audit overtime exposure by department.** Identify which teams have the highest proportion of employees on regular overtime and treat that as a structural risk flag, not an individual HR issue.

**2. Introduce a role tenure trigger.** Flag any employee who has been in the same role for 3 or more years with no lateral or upward movement for a proactive career conversation. This does not require a promotion every time — it requires acknowledgement and a plan.

**3. Segment compensation reviews by the $3,500 threshold.** Employees below this income level benefit most from pay adjustments as a retention tool. Above it, focus retention effort on non-financial drivers such as flexibility, recognition, and growth opportunity.

---

## Author

**Oluwatobi (Tobi) Abanishe**  
HR Business Analyst | People Analytics | Business Intelligence  
[LinkedIn](https://linkedin.com/in/oluwatobiabanishe) · [GitHub](https://github.com/TobiAbanishe) · tobi.abanishe@gmail.com
