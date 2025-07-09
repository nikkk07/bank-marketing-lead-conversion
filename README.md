# Bank Marketing Lead Conversion Prediction

## Overview

This project aims to predict whether a prospective customer will subscribe to a term deposit product after a direct marketing campaign conducted by a Portuguese bank. The dataset, originally from the UCI Machine Learning Repository (also available on Kaggle), contains information collected through phone calls during marketing campaigns.

By building a classification model, the goal is to help the bank improve targeting and optimize future campaigns.

---

## Dataset Details

- **Source:** [Kaggle – Bank Marketing Dataset](https://www.kaggle.com/datasets/willianoliveiragibin/bank-marketing)
- **Rows:** 45,000+
- **Target Variable:** `TARGET` — whether a customer subscribed (`yes`) or not (`no`)
- **Features:** 16 input variables including:
  - Age, Job, Marital status, Education
  - Account balance, Loan status, Contact type
  - Last contact day/month, Duration of contact
  - Previous outcome, Number of contacts during campaign

---

## Project Steps

1. **Exploratory Data Analysis (EDA)**
   - Checked class imbalance in the target variable
   - Identified that most customers did not subscribe
   - Explored patterns between features like `Job` and `Age` with the subscription rate

2. **Data Preprocessing**
   - Handled missing values by replacing 'unknown' where appropriate
   - Used One-Hot Encoding for categorical features
   - Encoded the target variable (`yes` → 1, `no` → 0)

3. **Baseline Model**
   - Built a Random Forest classifier using 80-20 train-test split
   - Evaluated with Accuracy and F1-score

4. **Improvement Using SMOTE**
   - Addressed the class imbalance using SMOTE (Synthetic Minority Oversampling Technique)
   - Re-trained the model with the balanced dataset
   - Observed improved F1-score, especially for the minority class (positive cases)

---

## Results

| Model             | Accuracy | F1 Score |
|------------------|----------|----------|
| Baseline (RF)     | 0.88     | 0.42     |
| SMOTE + RF        | 0.85     | 0.61     |

- **F1-score** improved significantly after using SMOTE.
- Slight drop in accuracy is acceptable as F1-score better captures performance on imbalanced data.

---

## Tools & Libraries Used

- Python 3.10
- Pandas, NumPy
- Matplotlib, Seaborn
- Scikit-learn
- Imbalanced-learn (for SMOTE)

---

## How to Run

1. Clone or download this repository.
2. Make sure the following libraries are installed:
   ```bash
   pip install pandas numpy matplotlib seaborn scikit-learn xgboost imbalanced-learn
