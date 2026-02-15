# Student Exam Score Prediction

## Overview
This project predicts student exam scores based on various factors such as study hours, attendance, previous scores, tutoring sessions, physical activity, parental involvement, and more.  
The project uses **machine learning models** trained in Python and provides a **web-based UI using Gradio** for users to enter inputs and get real-time predictions.

## Features
- Predicts student exam scores using trained ML models
- Handles both numeric and derived features
- Web-based interactive UI built with **Gradio**
- Easy to use sliders and dropdowns for all input features

## Dataset

This project uses a **Student Performance Factors** from Kaggle, commonly used for exam score prediction.

- Dataset name: Student Performance Factors  
- Link:https://www.kaggle.com/datasets/lainguyn123/student-performance-factors
  Note: The dataset is not included in this repository. Please download it directly from Kaggle using the link above.

## Dataset description
- Original dataset contains **21 features**, including both numeric and categorical features
- Missing values are handled by dropping or imputing as required
- Categorical features are converted to numeric using **One-Hot Encoding**
- For prediction, users enter the **most relevant features**, while the backend calculates additional derived features
- Some columns are dropped during preprocessing based on feature importance


## Models Trained
Two models were trained and tested:

1. **Random Forest Regressor**  
   - Accuracy / R²: ~0.67
   - Hyperparameter tuning via `GridSearchCV`  
   - Used for comparison, but lower performance

2. **Gradient Boosting Regressor (XGBoost compatible)**  
   - Accuracy / R²: ~0.77  
   - Hyperparameter tuning via `GridSearchCV`  
   - Best performance → selected for final predictions  
   - Parameters tuned: `n_estimators`, `learning_rate`, `max_depth`, `subsample`

> **Note:** Gradient Boosting / XGBoost model performed Well as compae to Random Forest, so it is used for the final prediction in the Gradio app.

## Exploratory Data Analysis (EDA)
- Visualized distribution of **Exam_Score** using histograms  
- Checked distributions of all numeric and categorical features  
- Visualized relationships between categorical features and target via boxplots  
- Correlation analysis conducted using heatmaps for all features  
- Log transformation applied to `Tutoring_Sessions` for better modeling

## How the Model Works
1. User enters inputs in the Gradio web UI using **sliders and dropdowns**
2. Backend calculates **derived features** automatically
3. Input features are arranged in the **same order as used in training**
4. Trained **Gradient Boosting Regressor** predicts exam score
5. Prediction is displayed in real-time on the UI

## Web Interface (Gradio)
- Uses sliders for numeric inputs: `Hours_Studied`, `Attendance`, `Previous_Scores`, `Tutoring_Sessions`, `Physical_Activity`  
- Uses dropdowns for categorical inputs: `Parental_Involvement`, `Access_to_Resources`, `Extracurricular_Activities`, `Motivation_Level`, `Internet_Access`, `Family_Income`, `Teacher_Quality`, `Peer_Influence`, `Learning_Disabilities`, `Parental_Education_Level`, `Distance_from_Home`  
- Interactive and easy for users to test predictions

## Technologies Used
- Python 3.x
- Pandas, NumPy
- Scikit-learn (Random Forest, Gradient Boosting, GridSearchCV)
- XGBoost / Gradient Boosting Regressor
- Matplotlib, Seaborn (for EDA & visualizations)
- Gradio (for web interface)


