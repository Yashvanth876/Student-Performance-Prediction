# Student Performance Prediction

## 📌 Overview

A Machine Learning regression project that predicts a student's **Mathematics Score** based on demographic information and performance in other academic areas.

The project follows an end-to-end Machine Learning workflow, including data analysis, preprocessing, model training, hyperparameter tuning, evaluation, and prediction on new data.

## 📊 Dataset

The dataset contains **1,000 student records** with the following features:

- Gender
- Race/Ethnicity
- Parental Level of Education
- Lunch Type
- Test Preparation Course
- Reading Score
- Writing Score

**Target Variable:** `math_score`

## 🔄 ML Workflow

```text
Dataset
   ↓
Exploratory Data Analysis
   ↓
Data Preprocessing
   ↓
Train-Test Split
   ↓
Feature Transformation
   ↓
Model Training
   ↓
Hyperparameter Tuning
   ↓
Model Evaluation
   ↓
Best Model Selection
   ↓
Prediction
```

## 🧹 Data Preprocessing

- Missing value handling using `SimpleImputer`
- One-hot encoding for categorical features
- Standard scaling for numerical features
- `ColumnTransformer` for combining preprocessing pipelines

## 🤖 Models Used

The following regression algorithms are trained and compared:

- Linear Regression
- Decision Tree Regressor
- Random Forest Regressor
- Gradient Boosting Regressor
- AdaBoost Regressor
- XGBoost Regressor
- CatBoost Regressor

**GridSearchCV** is used for hyperparameter tuning and selecting suitable model configurations.

## 📈 Evaluation

Model performance is evaluated using regression metrics such as:

- R² Score
- Mean Absolute Error (MAE)
- Root Mean Squared Error (RMSE)

The best-performing model is selected based on its evaluation performance and saved for making predictions on new student data.

## 📁 Project Structure

```text
student-performance-prediction/
│
├── data/
│   └── stud.csv
│
├── notebooks/
│   ├── 01_eda.ipynb
│   └── 02_model_training.ipynb
│
├── src/
│   ├── components/
│   │   ├── data_ingestion.py
│   │   ├── data_transformation.py
│   │   └── model_trainer.py
│   │
│   ├── pipeline/
│   │   └── predict_pipeline.py
│   │
│   ├── exception.py
│   ├── logger.py
│   └── utils.py
│
├── artifacts/
│   ├── train.csv
│   ├── test.csv
│   ├── preprocessor.pkl
│   └── model.pkl
│
├── requirements.txt
├── setup.py
└── README.md
```

## 🛠️ Technologies

- **Python**
- **Pandas**
- **NumPy**
- **Matplotlib**
- **Seaborn**
- **Scikit-learn**
- **XGBoost**
- **CatBoost**
- **Jupyter Notebook**

## 🎯 Key Learning Outcomes

This project demonstrates practical implementation of:

- Regression
- Exploratory Data Analysis
- Data preprocessing
- Feature transformation
- Model comparison
- Hyperparameter tuning
- Model evaluation
- Machine Learning pipelines
- Prediction on new data
- Data Engineering
- Software Development
