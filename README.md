# heart-disease-prediction-avenga-course
Final project for Data Science Course Avenga
# Heart Disease Prediction using Machine Learning

##  Project Overview

This project uses machine learning models to predict the presence of heart disease based on clinical features such as age, cholesterol, chest pain type, and heart rate.

The goal is to build a predictive system that can assist in early risk detection.

---

## Dataset

- Source: UCI Machine Learning Repository
- Dataset: Heart Disease (Cleveland)
- Samples: ~300 patients
- Target: Presence or absence of heart disease

---

##  Methods Used

### Exploratory Data Analysis (EDA)
- Distribution analysis
- Correlation analysis
- Clinical feature grouping (age, sex, cholesterol)

### Machine Learning Models
- Logistic Regression (baseline + optimized)
- Neural Network (MLPClassifier)
- SMOTE oversampling (experiment)
- Random Forest (optional benchmark)

---

##  Model Performance

| Model | Accuracy | ROC-AUC |
|------|---------|---------|
| Logistic Regression (Optimized) | 0.869 | 0.957 |
| Neural Network | ~0.86 | - |
| SMOTE Logistic Regression | 0.869 | 0.953 |

---

## Key Findings

- Logistic Regression performed best overall
- SMOTE did not improve performance due to balanced dataset
- Neural Network did not significantly outperform simpler models
- False negatives were minimized (~2 cases)

---

##  Clinical Insight

The best model achieved:
- High recall (~93%)
- Low false negatives
- Strong ROC-AUC performance

This makes it suitable as a **screening support tool**, not a medical diagnostic system.

---

## 📊 Model Performance Comparison

The models were evaluated using **5-fold stratified cross-validation**. Performance was assessed using accuracy, precision, recall, F1-score, ROC-AUC, and training time.

| Model | Train Time (sec) | CV Accuracy | CV Precision | CV Recall | CV F1 | CV ROC-AUC |
|:------|-----------------:|------------:|-------------:|----------:|-------:|-----------:|
| **Optimized Logistic Regression** | **0.041** | **0.835** | 0.838 | **0.798** | 0.815 | 0.911 |
| **SMOTE Logistic Regression** | 0.223 | **0.838** | **0.843** | **0.798** | **0.818** | **0.914** |
| **Neural Network (MLP)** | **0.038** | 0.776 | 0.775 | 0.762 | 0.758 | 0.887 |

### 🔍 Key Findings

- **Optimized Logistic Regression** provided the best balance between predictive performance, computational efficiency, and clinical interpretability.
- **SMOTE Logistic Regression** achieved marginal improvements in Accuracy (+0.3%), Precision, F1-score, and ROC-AUC; however, **Recall remained unchanged (79.8%)**, indicating that oversampling did not improve the model's ability to identify additional heart disease cases.
- The **Neural Network (MLP)** underperformed compared with both Logistic Regression models, achieving lower Accuracy (77.6%) and ROC-AUC (0.887). This suggests that a more complex model did not provide additional benefit for this relatively small tabular dataset.
- Although the SMOTE model achieved the highest overall metrics, its training time (**0.223 s**) was more than five times longer than the optimized Logistic Regression (**0.041 s**), while the performance gains were minimal.
- Based on these findings, the **Optimized Logistic Regression** model was selected as the final model for deployment due to its strong predictive performance, rapid training time, and high level of interpretability, making it the most appropriate choice for a clinical decision-support application.


## How to Run

```bash
pip install -r requirements.txt

## Dataset

This project uses the **UCI Heart Disease Dataset (Cleveland)**.

Dataset source:
https://archive.ics.uci.edu/dataset/45/heart+disease

The dataset can be downloaded directly from the UCI Machine Learning Repository.
