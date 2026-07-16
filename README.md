# Buy-Now-Pay-Later-Credit-Risk-Modeling-and-Customer-Analytics

End-to-end BNPL credit risk modeling project using R. Includes EDA, feature engineering, regression and classification models, clustering, and anomaly detection. Random Forest achieved best performance (AUC 0.768), highlighting effective prediction of default risk and customer segmentation insights.


🚀 **Project Overview**

Buy Now, Pay Later (BNPL) platforms have rapidly transformed consumer financing by offering flexible, short-term credit with minimal barriers. However, this accessibility introduces significant credit risk, making accurate default prediction critical.

This project applies end-to-end machine learning and analytics techniques to:

* Predict credit risk scores
* Classify default vs. non-default customers
* Identify customer segments
* Detect anomalies and high-risk behaviors

The workflow integrates data preprocessing, exploratory data analysis (EDA), supervised learning, unsupervised learning, and model evaluation to simulate a real-world fintech risk modeling pipeline.


📂 **Dataset**

* _**Source:**_ Kaggle BNPL Credit Risk Dataset
* _**Size:**_ ~10,000 records
* _**Features include:**_ Customer demographics, income and employment details, transaction history, product categories, risk score and default flag

⚙️ Tech Stack

* **Languages & Tools:** R, Kaggle API
* **Libraries:**
  * **Data Manipulation:** tidyverse, reshape2
  * **Modeling:** caret, glmnet, randomForest, e1071, rpart, nnet, kernlab
  * **Clustering & Anomaly Detection:** dbscan, isotree
  * **Visualization:** ggplot2, factoextra
  * **Evaluation:** pROC
  
🔧 **Project Pipeline**

__**1. Data Preparation:**__
   
* Converted categorical variables to factors
* Engineered feature: days_since_transaction
* Standardized target variable (default_flag)
* Removed redundant fields


**2. Exploratory Data Analysis (EDA):**
   
* Risk score distribution
* Default rates by customer segment
* Income vs. risk relationships
* Correlation heatmap


📌 **Key Insight:**

* Certain customer segments show significantly higher default rates
* Strong relationships exist between financial attributes and risk


**3. Train/Test Split**
   
* 80/20 split using stratified sampling
* Preserved class distribution for reliable evaluation


**4. Feature Scaling**
   
* Centering and scaling applied to numeric variables
* Critical for models like:
  * SVM
  * Neural Networks

🤖 **Machine Learning Models**

* 🔹 Regression (Risk Score Prediction)
* Linear Regression (baseline — affected by data leakage)
* Random Forest (robust, nonlinear modeling)


📊 _**Results:**_
* Linear Regression RMSE ≈ 0 → ⚠️ indicates data leakage
* Random Forest RMSE = 4.27 → realistic and reliable

🔹 **Classification (Default Prediction)**
 * **Baseline Models:**
   * Decision Tree
   * Logistic Regression

* **Tuned Models (5-Fold CV, ROC Optimization):**
  * Logistic Regression
  * Random Forest
  * SVM (Radial Kernel)

📊 _**AUC Comparison**:_

Model	AUC:
 * Random Forest	0.768
 * SVM	0.753
 * Logistic	0.740

🏆 Best Model: Random Forest


📈 **Evaluation Metrics:**

Confusion Matrix,
Accuracy,
Sensitivity (Recall),
Specificity,
ROC Curve,
AUC (Area Under Curve)

🧠 **Unsupervised Learning**

🔹 **Clustering**
* K-Means (k = 3)
* Hierarchical Clustering
* DBSCAN


📌 **Insights:**
* One dominant customer group
* Smaller clusters represent niche/high-risk segments
* DBSCAN successfully identifies noise (outliers)
  
🔹 **Anomaly Detection**
* Isolation Forest
* One-Class SVM

📌 **Purpose:**
* Detect fraudulent or unusual financial behavior
* Identify high-risk customers outside normal patterns

🧪 **Neural Network**

* Single hidden layer (5 neurons)
* Binary classification (default prediction)

📊 _**Results:**_
* Accuracy: 39.1%
* Sensitivity: 99.5%
* Specificity: 0.3%

⚠️ Issue:
* Model predicts nearly all observations as default
* Caused by class imbalance and poor convergence

🔍 **Key Findings**

* Random Forest is the most reliable model across tasks
* Linear Regression suffers from data leakage
* Logistic Regression underperforms without feature engineering
* SVM performs well but shows instability
* Neural Networks struggle with imbalanced tabular data
* Customer behavior is largely homogeneous with niche high-risk segments

📌 **Recommendations**

_1. Use Ensemble Models:_ Deploy Random Forest or Gradient Boosting (e.g., XGBoost)
   
_2. Handle Class Imbalance:_
* Apply:
   * SMOTE
   * Class weighting
   * Threshold tuning

_3. Prevent Data Leakage:_
 * Remove features derived from target variables
 * Validate feature independence

_4. Optimize Decision Thresholds:_
 * Move beyond default 0.5 cutoff
 * Align with business risk tolerance

_5. Add Explainability:_
* Feature importance
* SHAP values (future improvement)

_6. Improve Neural Networks:_   
* Regularization
* Better architecture
* Balanced datasets

_7. Leverage Unsupervised Learning:_
* Integrate clustering + anomaly detection into production pipelines

▶️ **How to Run**

1. Clone Repository:
* git clone https://github.com/yourusername/bnpl-credit-risk.git
* cd bnpl-credit-risk

2. Install Dependencies:
* Run the script — packages will auto-install:
* source("bnpl_analysis.R")

3. Kaggle Setup:
* Make sure Kaggle API is configured:
* kaggle datasets download -d shree0910/buy-now-and-pay-later-fintech-ml-dataset

📊 **Future Improvements**
* Implement XGBoost / LightGBM
* Add hyperparameter tuning with Bayesian optimization
* Deploy model via API (Plumber or FastAPI)
* Build interactive dashboard (Shiny / Tableau)
* Integrate real-time scoring pipeline (Spark / Kafka)

📎 **Project Structure**
├── data/
├── bnpl_analysis.R
├── README.md
└── outputs/
    ├── plots/
    ├── models/
    └── metrics/
    
💼 **Author**

Antoine Ward

Data Scientist | Healthcare & Fintech Analytics

LinkedIn: https://linkedin.com/in/antoine-ward-mph-2401581a1

GitHub: https://github.com/antoinewrd1
