# Student Performance Prediction using Machine Learning

An end-to-end **Machine Learning regression project** that predicts a student's **Mathematics Score** based on demographic, educational, and previous academic performance features.

The project demonstrates a complete ML workflow including **data ingestion, exploratory data analysis, data preprocessing, feature engineering, multiple regression models, hyperparameter tuning, model evaluation, and prediction on new data**.

---

## 📌 Project Overview

Student performance can be influenced by several factors such as parental education, test preparation, lunch type, and performance in other subjects.

In this project, a Machine Learning model is trained to predict a student's **Math Score** using the following information:

- Gender
- Race/Ethnicity
- Parental Level of Education
- Lunch Type
- Test Preparation Course
- Reading Score
- Writing Score

The problem is formulated as a **supervised regression problem** because the target variable, `math_score`, is a continuous numerical value.

### Objective

> Build a reliable regression pipeline that takes student information as input and predicts their expected Mathematics Score.

---

## 📊 Dataset

The project uses the **Student Performance Dataset**, containing **1,000 student records**.

### Features

| Feature | Description | Type |
|---|---|---|
| `gender` | Student's gender | Categorical |
| `race_ethnicity` | Student's race/ethnicity group | Categorical |
| `parental_level_of_education` | Highest parental education level | Categorical |
| `lunch` | Type of lunch received | Categorical |
| `test_preparation_course` | Whether the student completed test preparation | Categorical |
| `reading_score` | Reading examination score | Numerical |
| `writing_score` | Writing examination score | Numerical |

### Target Variable

`math_score`

The model learns the relationship between the input features and the student's Mathematics Score.

---

## 🔄 Machine Learning Workflow

The complete workflow is:

```text
Raw Dataset
     ↓
Data Ingestion
     ↓
Train / Test Split
     ↓
Exploratory Data Analysis
     ↓
Data Preprocessing
     ↓
Feature Transformation
     ↓
Multiple Regression Models
     ↓
Hyperparameter Tuning
     ↓
Model Evaluation
     ↓
Best Model Selection
     ↓
Save Trained Model
     ↓
Prediction on New Data
```

---

## 🔍 Exploratory Data Analysis

Before training the models, the dataset is analyzed to understand:

- Dataset structure
- Missing values
- Numerical feature distributions
- Categorical feature distributions
- Relationship between reading, writing and mathematics scores
- Effect of test preparation on performance
- Effect of parental education on student performance
- Correlation between numerical variables

Visualization and statistical analysis are performed using Python libraries such as **Pandas, Matplotlib and Seaborn**.

---

## 🧹 Data Preprocessing

The dataset contains both numerical and categorical variables, so separate preprocessing pipelines are used.

### Numerical Features

The numerical features are processed using:

```text
Missing Value Imputation
        ↓
Median
        ↓
StandardScaler
```

Numerical features:

```text
reading_score
writing_score
```

### Categorical Features

Categorical features are processed using:

```text
Missing Value Imputation
        ↓
Most Frequent Value
        ↓
One-Hot Encoding
        ↓
Scaling
```

Categorical features:

```text
gender
race_ethnicity
parental_level_of_education
lunch
test_preparation_course
```

A `ColumnTransformer` is used to combine both preprocessing pipelines.

---

## 🤖 Machine Learning Models

Multiple regression algorithms are trained and compared instead of relying on a single model.

The models include:

- Linear Regression
- Decision Tree Regressor
- Random Forest Regressor
- Gradient Boosting Regressor
- AdaBoost Regressor
- XGBoost Regressor
- CatBoost Regressor

The models are evaluated using the **R² score** and the model with the best performance is selected.

---

## ⚙️ Hyperparameter Tuning

To improve model performance, hyperparameters are optimized using:

```text
GridSearchCV
```

Different combinations of model parameters are tested and the best-performing configuration is selected.

This allows the project to compare:

```text
Default Model
        ↓
Different Hyperparameters
        ↓
Cross Validation
        ↓
Best Configuration
```

---

## 📈 Model Evaluation

The primary evaluation metric used is:

### R² Score

R² measures how well the model explains the variation in the target variable.

A higher R² score indicates better predictive performance.

The models are trained on the training dataset and evaluated on previously unseen test data.

---

## 🏗️ Project Structure

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

---

## 📂 Project Components

### 1. Data Ingestion

`data_ingestion.py`

Responsible for:

- Reading the raw dataset
- Creating training and testing datasets
- Saving processed dataset splits
- Starting the transformation pipeline

---

### 2. Data Transformation

`data_transformation.py`

Responsible for:

- Handling missing values
- Encoding categorical variables
- Scaling numerical variables
- Creating the preprocessing pipeline
- Saving the fitted preprocessor

---

### 3. Model Training

`model_trainer.py`

Responsible for:

- Training multiple regression models
- Performing hyperparameter tuning
- Comparing model performance
- Selecting the best model
- Saving the final trained model

---

### 4. Prediction Pipeline

`predict_pipeline.py`

Responsible for:

- Accepting new student information
- Applying the saved preprocessing pipeline
- Loading the trained model
- Generating the predicted Mathematics Score

---

### 5. Utility Functions

`utils.py`

Contains reusable functions for:

- Saving objects
- Loading objects
- Model evaluation
- Hyperparameter tuning

---

### 6. Exception Handling

`exception.py`

Provides custom exception handling to make errors easier to identify during development and execution.

---

### 7. Logging

`logger.py`

Creates logs that help track different stages of the ML pipeline and simplify debugging.

---

## 🛠️ Technologies Used

### Programming Language

- Python

### Data Processing

- Pandas
- NumPy

### Data Visualization

- Matplotlib
- Seaborn

### Machine Learning

- Scikit-learn
- XGBoost
- CatBoost

### Model Persistence

- Pickle / Dill

### Development Environment

- Jupyter Notebook
- VS Code

---

## 🚀 Installation

### 1. Clone the repository

```bash
git clone <your-github-repository-url>
cd student-performance-prediction
```

### 2. Create a virtual environment

```bash
python -m venv venv
```

### 3. Activate the environment

Windows:

```bash
venv\Scripts\activate
```

### 4. Install dependencies

```bash
pip install -r requirements.txt
```

---

## ▶️ Running the Project

### Step 1 — Explore the Dataset

Open:

```text
notebooks/01_eda.ipynb
```

Run the notebook to understand the dataset and perform exploratory data analysis.

### Step 2 — Train the Models

Open:

```text
notebooks/02_model_training.ipynb
```

or execute the modular training pipeline.

The pipeline will:

```text
Load Dataset
     ↓
Split Dataset
     ↓
Transform Features
     ↓
Train Models
     ↓
Tune Hyperparameters
     ↓
Evaluate Models
     ↓
Select Best Model
     ↓
Save Model
```

### Step 3 — Make Predictions

Provide a new student's information to the prediction pipeline.

Example:

```text
Gender: Male
Race/Ethnicity: Group C
Parental Education: Bachelor's Degree
Lunch: Standard
Test Preparation: Completed
Reading Score: 85
Writing Score: 82
```

The trained model then produces an estimated Mathematics Score.

---

## 📌 Example Prediction Flow

```text
New Student Data
       ↓
Create DataFrame
       ↓
Load preprocessor.pkl
       ↓
Transform Features
       ↓
Load model.pkl
       ↓
Generate Prediction
       ↓
Predicted Math Score
```

Example output:

```text
Predicted Math Score: 84.5
```

---

## 💡 Key Machine Learning Concepts Demonstrated

This project demonstrates practical implementation of:

- Supervised Learning
- Regression
- Exploratory Data Analysis
- Feature Engineering
- Missing Value Handling
- One-Hot Encoding
- Feature Scaling
- ColumnTransformer
- Train/Test Split
- Cross Validation
- GridSearchCV
- Model Comparison
- Hyperparameter Tuning
- Model Evaluation
- Model Serialization
- Prediction Pipelines
- Modular ML Project Structure
- Exception Handling
- Logging

---

## 🔮 Future Improvements

Possible improvements include:

- Add additional student performance features
- Perform more extensive feature engineering
- Experiment with advanced ensemble models
- Add cross-validation based model comparison
- Track experiments using MLflow
- Add explainable AI using SHAP
- Build a Streamlit prediction interface
- Deploy the model as an API
- Add automated testing
- Implement CI/CD for the ML pipeline

---

## 🎯 Learning Outcome

This project demonstrates how to move from a simple Jupyter Notebook ML experiment to a **structured and reusable machine learning pipeline**.

The main objective is not only to train a model but also to understand how different stages of a real-world ML project are organized:

```text
Data
 ↓
EDA
 ↓
Preprocessing
 ↓
Model Development
 ↓
Hyperparameter Tuning
 ↓
Evaluation
 ↓
Model Persistence
 ↓
Prediction
```

---

## 👨‍💻 Author

**Yashvanth Kanike**

Computer Science Engineering Student

Interests:

- Machine Learning
- Data Science
- Data Engineering
- Software Development
