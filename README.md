# 🌦️ Rainfall Prediction in Australia

## 📌 Problem Statement
The Bureau of Meteorology collects daily weather observations across Australia.  
As a data scientist, the goal is to **predict whether it will rain tomorrow** at a given location, using today's weather conditions.

Dataset: [Rain in Australia](https://www.kaggle.com/datasets/jsphyg/weather-dataset-rattle-package)  
(~10 years of daily weather records, 145,000+ rows).  

Target variable: **RainTomorrow** (`Yes`/`No`).

---

## ⚙️ Project Workflow

### 1. Exploratory Data Analysis (EDA)
- Inspected dataset structure, types, and missing values.  
- Target distribution (`RainTomorrow`: Yes/No).  
- Explored features (rainfall, humidity, temperature, wind, etc.).  

### 2. Feature Engineering & Preprocessing
- Removed rows where target was missing.  
- Imputed missing values using **SimpleImputer**.  
- Scaled numeric features with **MinMaxScaler**.  
- Encoded categorical features with **OneHotEncoder**.  
- Split data into **training/validation** sets with time awareness.

### 3. Model Training
Trained and compared multiple models:
- **Decision Tree Classifier**  
  - Baseline model.  
  - Train accuracy: 100%, Validation: ~79% → overfitting.  

- **Random Forest Classifier**  
  - Ensemble of decision trees.  
  - Improved generalization, reduced overfitting.  
  - Best performing model overall.  

- **Logistic Regression**  
  - Linear baseline model for classification.  
  - More interpretable, but slightly weaker performance compared to Random Forest.  

### 4. Model Evaluation
Metrics used:
- Accuracy  
- Precision, Recall, F1-score  
- Confusion Matrix  

Results:
- Decision Tree → Overfit, poor generalization.  
- Random Forest → Best balance of accuracy and generalization.  
- Logistic Regression → Good interpretability, reasonable accuracy.  

---

## 📊 Key Insights
- **Humidity, Rainfall, WindGustSpeed, Location** are strong predictors.  
- Decision Trees alone tend to overfit.  
- **Random Forests** outperform single trees by averaging many models.  
- Logistic Regression offers interpretability but lower performance.  

---

## 💻 Usage

### Install requirements
```bash
pip install pandas numpy scikit-learn matplotlib seaborn joblib
