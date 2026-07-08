# Online-Shoppers-Purchase-Prediction-ML

# Online Shoppers Purchase Intention Prediction using Machine Learning

Predicting whether an online shopper will complete a purchase based on browsing behavior using Machine Learning.

## Project Overview

Most e-commerce visitors browse products without making a purchase. Identifying high-intent visitors helps businesses deliver personalized offers, improve conversion rates, and optimize marketing spend.

This project builds and compares multiple machine learning models to predict purchase intention using customer browsing behavior. Starting from a baseline Logistic Regression model, the project progressively improves performance through feature engineering, handling class imbalance, and hyperparameter tuning.

---

##  Business Objective

* Predict whether a visitor will make a purchase.
* Identify the most influential factors affecting purchase intention.
* Compare multiple classification models.
* Recommend the best model for real-world deployment.

---

## Dataset

**Source:** UCI Online Shoppers Purchasing Intention Dataset

* **Rows:** 12,330
* **Features:** 18
* **Target Variable:** Revenue
* **Problem Type:** Binary Classification

### Engineered Features

* TotalPages
* TotalDuration

---

## Data Preprocessing

* Removed duplicate records
* Verified missing values
* Standardized categorical values
* Feature Engineering
* Outlier Analysis (IQR)
* Retained genuine business outliers
* Log1p Transformation
* One-Hot Encoding
* Robust Scaling
* Train-Test Split (80:20, Stratified)

---

## Machine Learning Experiments

### Experiment 1

**Baseline Logistic Regression**

* Built a simple baseline model
* No transformations
* No class balancing

---

### Experiment 2

**Logistic Regression + Log1p Transformation**

* Reduced feature skewness
* Improved model performance
* Better class separation

---

### Experiment 3

**Logistic Regression + Log1p + Class Weight**

* Addressed class imbalance
* Increased Recall for minority class
* Suitable when missing buyers is costly

---

### Experiment 4

#### Decision Tree

* GridSearchCV
* Overfitting reduction
* Hyperparameter tuning

#### Random Forest

* RandomizedSearchCV
* Hyperparameter tuning
* Best overall model

---

# Model Comparison

| Model                                      |  Accuracy | Precision |   Recall |       F1 |   ROC-AUC |
| ------------------------------------------ | --------: | --------: | -------: | -------: | --------: |
| Logistic Regression                        |     89.0% |      0.77 |     0.42 |     0.54 |     0.902 |
| Logistic Regression + Log1p                | **90.3%** |      0.72 |     0.61 |     0.66 |     0.926 |
| Logistic Regression + Log1p + Class Weight |     87.0% |      0.56 | **0.81** |     0.66 |     0.929 |
| Decision Tree (Tuned)                      |     85.0% |      0.52 | **0.81** |     0.63 |     0.919 |
| **Random Forest (Tuned)** ⭐               | **89%**   |  **0.64** | **0.75** | **0.69** | **0.929** |

---

#  Final Model

## Tuned Random Forest

### Performance

* Accuracy: **89%**
* Precision: **0.64**
* Recall: **0.75**
* F1-Score: **0.69**
* ROC-AUC: **0.929**

The tuned Random Forest delivered the best balance between Precision and Recall while achieving the highest F1-Score and excellent ROC-AUC, making it the recommended model for deployment.

---

# Key Insights

* PageValues is the strongest predictor of purchase intention.
* Returning visitors contribute most purchase sessions.
* Product engagement significantly influences conversion.
* Hyperparameter tuning greatly reduced overfitting.
* F1-Score and ROC-AUC proved more informative than Accuracy due to class imbalance.

---

# 💼 Business Recommendations

* Target visitors with high predicted purchase probability.
* Personalize offers for returning visitors.
* Improve landing pages with high exit rates.
* Focus campaigns during high-conversion months.
* Use PageValues and visitor engagement metrics for customer segmentation.

---

# 🛠️ Tech Stack

**Programming**

* Python

**Libraries**

* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn

**Machine Learning**

* Logistic Regression
* Decision Tree
* Random Forest
* GridSearchCV
* RandomizedSearchCV

**Development**

* Jupyter Notebook
* Git
* GitHub


---

# Future Improvements

* Deploy the model using Streamlit or Flask.
* Experiment with XGBoost and LightGBM.
* Build a real-time prediction interface.
* Monitor model performance on new customer sessions.

---

## 👩‍💻 Author

**Komal Kakkar**

Aspiring Data Analyst | Python | SQL | Power BI | Machine Learning

If you found this project helpful, feel free to ⭐ the repository.
