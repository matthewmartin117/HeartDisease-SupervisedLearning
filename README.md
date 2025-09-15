# Heart Disease Prediction Using Ensembled Decision Trees

**Author:** Matthew Martin

## Overview

This project aims to predict the likelihood of heart disease using survey data from the Behavioral Risk Factor Surveillance System (BRFSS), a health-related telephone survey conducted by the CDC. Machine learning models, including decision trees, random forests, and gradient boosting classifiers, were applied to classify individuals as having or not having heart disease based on lifestyle, demographic, and medical features.

## Dataset

- **Source:** [Kaggle: Heart Disease Health Indicators Dataset](https://www.kaggle.com/datasets/alexteboul/heart-disease-health-indicators-dataset/data)  
- **Survey Year:** 2022  
- **Number of Samples:** 400,000  
- **Number of Features:** 40  
- **Target Variable:** `HadHeartAttack`  
- **Class Balance:** Imbalanced (`No` >> `Yes`)

**Note:** The dataset contains both categorical and numerical features. Data preprocessing included encoding categorical variables and addressing class imbalance via undersampling.

## Approach

1. **Data Exploration and Visualization**  
   - Examined distributions of numerical features and categorical features against heart disease incidence.  
   - Identified important features such as age, BMI, smoking status, alcohol consumption, and COVID history.

2. **Data Preprocessing**  
   - Converted categorical variables to numeric using `LabelEncoder`.  
   - Addressed missing values and class imbalance (minority class oversampling/majority class undersampling).

3. **Modeling**  
   - **Baseline:** Decision Tree Classifier with balanced class weights.  
   - **Ensembled Models:** Random Forest and Gradient Boosting Classifiers to improve recall and precision.  
   - **Hyperparameter Tuning:** Grid search used to optimize Gradient Boosting parameters for better recall.

4. **Threshold Adjustment**  
   - Adjusted classification threshold to increase recall, prioritizing detection of true positive cases.

## Results

- **Baseline Decision Tree:**  
  - Accuracy: 92%  
  - Recall (Heart Disease): 26%  
  - Precision (Heart Disease): 26%  

- **Random Forest:**  
  - Accuracy: 95%  
  - Recall (Heart Disease): 11%  
  - Precision (Heart Disease): 59%  

- **Gradient Boosting:**  
  - Accuracy: 95%  
  - Recall (Heart Disease): 25%  
  - Precision (Heart Disease): 57%  

- **After Undersampling & Hyperparameter Tuning:**  
  - Accuracy: 82%  
  - Recall (Heart Disease): 65%  
  - Precision (Heart Disease): 76%  

**Conclusion:** Gradient Boosting with tuned parameters and undersampling achieved the best balance between recall and precision. Adjusting the decision threshold further increased recall to 90%, allowing the model to capture most true positive cases, making it suitable for medical screening applications.

## Key Takeaways

- Handling class imbalance is critical in medical datasets.  
- Recall is prioritized in healthcare applications to minimize missed diagnoses.  
- Ensemble methods improve prediction performance over simple decision trees.  
- Threshold tuning provides a practical approach to balance sensitivity and specificity.

## Future Work

- Explore additional feature engineering using comorbidity and lifestyle interactions.  
- Test alternative oversampling methods (e.g., SMOTE) to further improve recall.  
- Deploy the model in a real-world clinical screening environment for prospective evaluation.

