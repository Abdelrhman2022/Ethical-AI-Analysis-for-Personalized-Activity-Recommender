# Ethical-AI-Analysis-for-Personalized-Activity-Recommender

## 📱 Project Summary

IDOOU is a mobile app that provides personalized activity recommendations based on user preferences and context. This project focuses on building a budget prediction model using user data, and evaluating the fairness and ethical implications of that model. The app leverages features like **gender**, **age**, and **education level** to recommend activities such as visiting a park, hiking, or going to the library.

### 🧠 Problem Statement

We aim to determine whether users with higher education levels (Bachelor's and Master's degrees) are a privileged group in terms of budget allocation (≥ $300) compared to users with only a high school education. Using a synthetic dataset of 300,000 participants, we will:

- Train and evaluate two machine learning models to predict user budget.
- Analyze fairness and bias in both data and model predictions using IBM's **AIF360**.
- Implement and evaluate **bias mitigation techniques**.
- Document the process in a **Model Card**.

---

## ✅ Project Steps

### 1. Data Exploration & Fairness Analysis
- Check for missing data in `gender`, `age`, `education_level`, and `budget`.
- Visualize:
  - Budget distribution by `education_level`
  - Budget vs `gender` and `age`
- Convert dataset to `BinaryLabelDataset` using AIF360.
- Compute fairness metrics:
  - **Disparate Impact**
  - **Statistical Parity Difference**
  - **Equal Opportunity Difference**

### 2. Model Training
- Train two models (e.g., `Logistic Regression`, `Random Forest`).
- Evaluate:
  - Predictive performance: Accuracy, MAE, RMSE
  - Fairness using AIF360 metrics

### 3. Fairness Evaluation
- Compare performance and fairness of both models.
- Identify which groups may be disadvantaged by predictions.

### 4. Bias Mitigation
Apply one or more of the following strategies:
- **Pre-processing** (e.g., `Reweighing`, `DisparateImpactRemover`)
- **In-processing** (e.g., `Adversarial Debiasing`)
- **Post-processing** (e.g., `Reject Option Classification`)

Evaluate the improvement in fairness and changes to model performance.

### 5. Explainability
- Apply explainability tools (`SHAP`, `LIME`) to understand model decisions.
- Investigate whether predictions differ based on sensitive features.

---

## 📄 Model Card Outline

### 🧠 Model Details
- **Type**: Regression (e.g., Logistic Regression / Random Forest)
- **Input Features**: gender, age, education_level
- **Target Variable**: user budget (USD)

### 🎯 Intended Use
- Recommending local activities based on personal budget and preferences.

### ⚠️ Ethical Considerations
- Risk of **discrimination by education level**
- Risk of **proxy bias** (education level as proxy for income or class)
- Exclusion of users with missing data may compound bias

### 🔬 Limitations
- Synthetic dataset; may not reflect real-world diversity
- Education level might not correlate with actual financial situation

### 📊 Fairness Evaluation
- **Privileged group**: Users with Bachelor's or Master's degrees
- **Unprivileged group**: Users with only High School education
- Metrics:
  - Statistical Parity Difference
  - Equal Opportunity Difference
  - Disparate Impact

### 🛠 Bias Mitigation Techniques
- Selected strategy: e.g., Reweighing (pre-processing)
- Comparison of pre- and post-mitigation metrics

---

## 📌 Notes

- Dataset: 300,000 synthetic user profiles
- Toolkit: [IBM AIF360](https://aif360.readthedocs.io/en/latest/)
- Optional integrations: Explainability tools like SHAP, LIME

---

## 🚀 Goal

This project simulates a realistic ethical AI workflow—analyzing the use case, evaluating technical bias, and documenting results transparently in a model card. The approach mirrors industry best practices for responsible AI development and governance.

