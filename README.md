# Student Performance Prediction System

## Overview
This project is a machine learning-based student performance prediction system. It predicts whether a student is likely to **Pass** or **Fail** and also estimates the student's final marks percentage.

The system uses student academic and behavioral features such as attendance, study hours, previous grades, extracurricular activities, parental support, and online class participation.

## Project Notebook
Main notebook:

```text
Student_Performance_Prediction_System.ipynb
```

## Objectives
- Predict student performance as **Pass** or **Fail**
- Predict final marks percentage
- Compare multiple machine learning models
- Select the best-performing model
- Provide explainability using feature importance and SHAP
- Save the final trained system for fast demo/testing

## Dataset
The project uses a student performance dataset:

```text
student_performance_updated_1000.csv
```

The target variables are created from the `FinalGrade` column.

### Target Rule
```text
FinalGrade >= 70  -> Pass
FinalGrade < 70   -> Fail
```

A new target column named `Performance` is created:
- `1` = Pass
- `0` = Fail

## Main Features Used
The system uses available student-related features such as:

- Gender
- Attendance Rate
- Study Hours Per Week
- Previous Grade
- Extracurricular Activities
- Parental Support
- Daily Study Hours
- Attendance Percentage
- Online Classes Taken

Some columns such as `StudentID`, `Name`, and `FinalGrade` are dropped before training the classification model.

## Models Used

### Classification Models
For Pass/Fail prediction, the following models are used:

1. Logistic Regression
2. Decision Tree Classifier
3. Random Forest Classifier

The best classification model is selected based on **F1-score**.

### Regression Models
For marks percentage prediction, the following models are used:

1. Linear Regression
2. Decision Tree Regressor
3. Random Forest Regressor

The best regression model is selected based on the lowest **RMSE**.

## Preprocessing
The preprocessing pipeline includes:

- Handling missing numeric values using mean imputation
- Handling missing categorical values using most frequent imputation
- Standard scaling for numeric features
- One-hot encoding for categorical features
- Train-test split with 80% training and 20% testing

## Evaluation Metrics

### Classification Metrics
- Accuracy
- Precision
- Recall
- F1-score
- Fail Recall
- Pass Recall
- Cross-validation F1-score
- Confusion Matrix

### Regression Metrics
- MAE
- RMSE
- R² Score

## Explainability
The project includes explainability methods to understand model predictions:

- Feature Importance
- Lightweight SHAP Summary Plot

These help identify which student-related factors are most important for predicting performance.

## Saved Model System
The final trained system is saved as:

```text
student_performance_final_system.pkl
```

The saved system includes:

- Best classification model
- Best regression model
- Model names
- Evaluation results
- Raw input feature names
- Input template
- Feature importance data
- Pass mark threshold

## Fast Demo Mode
The notebook includes a fast demo mode where the saved model system can be loaded directly without retraining.

Users can manually enter student information and get:

- Predicted Pass/Fail status
- Predicted marks percentage
- Prediction probability
- Actionable suggestions for improvement

## Installation

Install the required libraries:

```bash
pip install numpy pandas matplotlib scikit-learn shap joblib
```

If running on Google Colab, the notebook will mount Google Drive and save the dataset/model files inside:

```text
/content/drive/MyDrive/student_project
```

## How to Run

1. Open the notebook in Google Colab or Jupyter Notebook.
2. Upload or place the dataset file:
   ```text
   student_performance_updated_1000.csv
   ```
3. Run all notebook cells step by step.
4. The system will train classification and regression models.
5. The best models will be selected automatically.
6. The final model system will be saved as:
   ```text
   student_performance_final_system.pkl
   ```
7. Use the manual input testing section or fast demo mode to test new student data.

## Project Workflow

```text
Load Dataset
     ↓
Data Cleaning
     ↓
Create Pass/Fail Target
     ↓
Preprocessing
     ↓
Train-Test Split
     ↓
Train Classification Models
     ↓
Select Best Classification Model
     ↓
Train Regression Models
     ↓
Select Best Regression Model
     ↓
Feature Importance & SHAP Explainability
     ↓
Save Final System
     ↓
Manual Student Performance Prediction
```

## Technologies Used
- Python
- Pandas
- NumPy
- Matplotlib
- Scikit-learn
- SHAP
- Joblib
- Google Colab

## Repository Structure

```text
Student-Performance-Prediction/
│
├── Student_Performance_Prediction_System.ipynb
├── README.md
├── requirements.txt
└── student_performance_final_system.pkl
```

> Note: Large datasets and model files can be excluded from GitHub using `.gitignore`.

## Future Improvements
- Build a Streamlit web application
- Add more advanced models such as XGBoost or LightGBM
- Improve dataset quality and feature engineering
- Add student risk-level categorization
- Deploy the system online
- Add a dashboard for teachers/admins

## Author
Developed as part of a Machine Learning & Deep Learning Lab project.
