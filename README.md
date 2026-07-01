#  VinQCheck: An Intelligent Wine Quality Assessment

VinQCheck is a machine learning-based system that predicts the quality of red wine using its physicochemical properties. Built on the Kaggle "Vinho Verde" red wine dataset, the project compares multiple ML algorithms to identify the most accurate model for quality prediction, helping winemakers and quality analysts make faster, data-driven decisions.

##  Overview

Wine quality assessment is traditionally done through sensory (expert) evaluation, which is time-consuming and expensive. VinQCheck automates this process by learning patterns between chemical composition and quality ratings, enabling quick and consistent predictions on a 0–10 scale.

##  Objectives

- Predict red wine quality using physicochemical input features
- Compare multiple classification algorithms to find the best performer
- Identify which chemical properties most influence wine quality
- Handle class imbalance in the target variable for reliable predictions

##  Dataset

- **Source:** Kaggle — Red Wine Quality (Vinho Verde, Portuguese red wine)
- **Samples:** 1,599
- **Features:** 11 physicochemical inputs (fixed acidity, volatile acidity, citric acid, residual sugar, chlorides, free/total sulfur dioxide, density, pH, sulphates, alcohol)
- **Target:** Quality score (0–10, based on sensory data)
- No missing values were found in the dataset.

##  Methodology

1. **Data Preprocessing** – Verified data types and checked for missing/inconsistent values
2. **Exploratory Data Analysis** – Univariate (histograms) and bivariate (boxplots) analysis to study feature distributions and their relationship with wine quality
3. **Feature Engineering & Selection** – Used Random Forest's Feature Importance to identify key predictors; low-importance features (citric acid, free sulfur dioxide) were candidates for removal
4. **Correlation Analysis** – Checked multicollinearity via correlation matrix (no strong collinearity found)
5. **Handling Class Imbalance** – Applied **SMOTE** (Synthetic Minority Over-sampling Technique) to balance the target classes
6. **Model Building** – Trained and evaluated six models:
   - Logistic Regression
   - Support Vector Classifier (SVC)
   - K-Nearest Neighbors (KNN)
   - Decision Tree
   - Random Forest
   - Gradient Boosting Classifier
   - An Artificial Neural Network (ANN) was also built using TensorFlow
7. **Model Evaluation** – Compared models using Accuracy, Precision, Recall, and F1-score

##  Key Findings

- **Random Forest** achieved the best overall performance:
  | Metric | Score |
  |---|---|
  | Accuracy | 0.91 |
  | Precision | 0.87 |
  | Recall | 0.93 |
  | F1-score | 0.91 |
- **Alcohol content** is the strongest predictor of wine quality, followed by sulphates and volatile acidity
- Alcohol, sulphates, and citric acid are **positively correlated** with quality
- Volatile acidity, density, and pH are **negatively correlated** with quality
- The target variable was highly imbalanced, which affected prediction performance on minority quality classes even after SMOTE

##  Tech Stack

- **Language:** Python
- **Libraries:** Pandas, NumPy, Scikit-learn, Matplotlib, Seaborn, TensorFlow
- **Environment:** Google Colab / Jupyter Lab

##  Results Summary

For every 100 red wine samples, the final model correctly predicted quality for approximately 69 wines. Performance was strongest for mid-range quality classes (which had more training data) and weaker for minority classes, even after oversampling.

##  Team

Developed as a college research project by a team of undergraduate students, Department of Information Technology, Rashtrasant Tukdoji Maharaj Nagpur University, Nagpur, Maharashtra, India, under faculty guidance.

##  Publication

This work was published in the *International Journal of Innovative Science and Research Technology (IJISRT)*, Volume 8, Issue 12, December 2023.

##  References

Dataset and related literature sourced from Kaggle and peer-reviewed journals on wine quality prediction (see full reference list in the published paper).
