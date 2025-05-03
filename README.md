🚗 Capstone Project: Predicting Accident Severity in the US Using Machine Learning

This repository contains the complete pipeline and analysis for a capstone project aimed at predicting the severity of traffic accidents across the United States using the US Accidents dataset. The dataset comprises approximately 7.7 million records collected from 49 states between 2016 and 2023, containing over 40 diverse features related to location, weather, time, and road conditions.

🧠 Project Objective
The primary goal of the project was to build an efficient and interpretable binary classification model that could differentiate between high-severity and low-severity accidents. The model is designed to assist in traffic management, safety policy development, and emergency response planning by identifying critical conditions that lead to more severe accidents.


📦 Dataset Summary
->Size: 7.7 million records

->Features: 40+ (e.g., latitude, weather, road type, timestamps)

->Label: Severity (Levels 1–4, later reduced to binary: low [0] and high [1])

->Challenges: High dimensionality, class imbalance, missing values, and outliers


🧹 Data Preprocessing & Cleaning

->Stratified Sampling: Reduced the dataset to ~300,000 rows while maintaining the class distribution to optimize model training without compromising data integrity.

->Missing Values: Applied mode imputation for categorical features and KNN imputation for continuous features to preserve data relationships.

->Data Transformation: Converted date/time fields for temporal feature extraction; converted booleans to integers for modeling.

->Outlier Handling: Used RobustScaler to normalize data while preserving important outlier information.


🛠️ Feature Engineering & Selection

->Feature Reduction: Removed redundant or high-cardinality columns (e.g., Street, Description, Zipcode).

->New Features: Engineered time-based features like year, month, weekday, rush-hour flag, and traffic delay.

->Encoding: One-hot encoding (with drop-first strategy) was used for categorical variables to avoid implicit ordinal relationships.

->Correlation Management: Removed highly correlated features to avoid multicollinearity and reduce noise.


📊 Exploratory Data Analysis (EDA)

->Univariate & Bivariate Analysis: Used box plots, bar plots, and stacked visualizations to reveal distribution patterns and relationships with severity.

->Hypothesis Testing: Applied Chi-Square tests to assess associations between categorical features and accident severity.


🏷️ Label Engineering & Class Imbalance

->Binary Labeling: Merged original severity levels into:

    o 0 → Low severity (Levels 1 & 2)

    o 1 → High severity (Levels 3 & 4)

->Class Imbalance Handling: Evaluated SMOTE, Random Oversampling, and ADASYN. ADASYN was selected for its ability to focus on harder-to-learn minority samples, improving generalization and model robustness.


🤖 Modeling & Evaluation

->Models Tried: K-Nearest Neighbors (KNN), Naïve Bayes, Decision Tree, Random Forest, Gradient Boosting, and XGBoost.

->Evaluation Metrics: Confusion matrix, classification report, ROC-AUC curves, and Youden’s J statistic to select optimal probability thresholds.

->Hyperparameter Tuning: Compared GridSearchCV, RandomizedSearchCV, and HyperOpt. HyperOpt yielded the best results with fewer iterations and better optimization in high-dimensional space.


🏆 Best Model & Final Performance

->Model: XGBoost

->Performance: Achieved a recall of 0.70 for both classes, balancing true positive rate across high- and low-severity predictions.

->Why Recall Matters: In accident severity prediction, minimizing false negatives is critical—failing to predict a high-severity accident could lead to higher risks for drivers and delayed emergency response.


✅ Key Takeaways
->The pipeline successfully tackles real-world imbalanced classification problems in a high-volume, multi-feature dataset.

->The project integrates rigorous preprocessing, targeted feature engineering, and robust evaluation techniques.

->The final model can be adapted and deployed to assist stakeholders in public safety, smart city planning, or insurance analytics.


Note:- Dataset is big kindly download it directly from kaggle via this link https://www.kaggle.com/datasets/sobhanmoosavi/us-accidents
