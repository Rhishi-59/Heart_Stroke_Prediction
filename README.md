#  Heart Stroke Prediction using Machine Learning

[![Python Version](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://www.python.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](https://opensource.org/licenses/MIT)
[![Framework](https://img.shields.io/badge/Scikit--Learn-Machine%20Learning-orange.svg)](https://scikit-learn.org/)

An end-to-end machine learning project designed to assess and predict the risk of stroke in patients based on physiological indicators, medical history, and lifestyle factors.

---

## 📌 Project Overview

According to the World Health Organization (WHO), stroke is one of the leading causes of death and disability globally. Early identification of high-risk individuals enables timely medical intervention and lifestyle modifications.

This repository implements a data science pipeline that:
- Cleans and preprocesses clinical patient data.
- Handles class imbalance typical in medical diagnosis datasets.
- Trains and evaluates supervised machine learning classification models.
- Analyzes key risk factors driving stroke prediction.

---

## 📊 Dataset Features

The model utilizes key demographic, lifestyle, and health indicators:

| Feature | Description | Type |
| :--- | :--- | :--- |
| `gender` | Male, Female, or Other | Categorical |
| `age` | Age of the patient | Numerical |
| `hypertension` | `0` = No hypertension, `1` = Diagnosed with hypertension | Binary |
| `heart_disease` | `0` = No heart disease, `1` = Diagnosed with heart disease | Binary |
| `ever_married` | `No` or `Yes` | Categorical |
| `work_type` | `children`, `Govt_job`, `Never_worked`, `Private`, `Self-employed` | Categorical |
| `Residence_type` | `Rural` or `Urban` | Categorical |
| `avg_glucose_level`| Average blood glucose level | Numerical |
| `bmi` | Body Mass Index (BMI) | Numerical |
| `smoking_status` | `formerly smoked`, `never smoked`, `smokes`, or `Unknown` | Categorical |
| **`stroke`** | **Target variable**: `1` if patient suffered a stroke, `0` otherwise | Binary |

---

## ⚙️ Methodology & Pipeline

1. **Exploratory Data Analysis (EDA):**
   - Analyzing feature distributions, correlations, and target variable skewness.
2. **Data Cleaning & Preprocessing:**
   - Imputing missing numerical values (e.g., median imputation for `bmi`).
   - One-Hot / Label encoding for categorical variables.
   - Feature scaling (StandardScaler / MinMaxScaler) for numerical features.
3. **Handling Class Imbalance:**
   - Medical datasets typically contain far fewer positive stroke cases. Techniques such as **SMOTE** (Synthetic Minority Over-sampling Technique) or class weighting are applied to avoid biased classifiers.
4. **Model Training & Evaluation:**
   - Algorithms evaluated:
     - Logistic Regression
     - Decision Trees & Random Forest
     - Support Vector Machines (SVM)
     - Gradient Boosting (XGBoost / LightGBM)
   - Metrics focused on recall and area under the curve to minimize false negatives:
     - **Recall / Sensitivity**
     - **ROC-AUC Score**
     - **F1-Score & Precision**

---

## 📁 Repository Structure

```text
Heart_Stroke_Prediction/
│
├── data/
│   └── healthcare-dataset-stroke-data.csv   # Dataset
│
├── notebooks/
│   └── stroke_prediction_eda_model.ipynb     # Exploration & model experiments
│
├── models/
│   └── stroke_model.pkl                      # Serialized trained model
│
├── requirements.txt                          # Project dependencies
```

---

## 🚀 Getting Started

### Prerequisites

Ensure you have **Python 3.8+** installed.

### 1. Clone the Repository

```bash
git clone https://github.com/Rhishi-59/Heart_Stroke_Prediction.git
cd Heart_Stroke_Prediction
```

### 2. Set Up Virtual Environment

```bash
# On Linux/macOS:
python3 -m venv venv
source venv/bin/activate

# On Windows:
python -m venv venv
venv\Scripts\activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Run the Analysis 

```bash
streamlit run app.py
```
enter an email when prompted

---

## 📈 Key Insights & Risk Factors

From feature importance and correlation analyses, the primary risk drivers identified are:
- **Age:** Older demographics show significantly higher risk factors.
- **Average Glucose Level:** High glucose levels exhibit strong correlation with stroke occurrence.
- **Hypertension & Pre-existing Heart Disease:** Critical clinical multipliers for elevated risk.

---

## 🤝 Contributing

Contributions, feedback, and issue reports are welcome!
1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/NewFeature`)
3. Commit your Changes (`git commit -m 'Add NewFeature'`)
4. Push to the Branch (`git push origin feature/NewFeature`)
5. Open a Pull Request
