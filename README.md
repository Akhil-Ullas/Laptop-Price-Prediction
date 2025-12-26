

# 💻 Laptop Price Prediction — Machine Learning Regression Project

This project builds a machine-learning regression model to predict laptop prices based on hardware specifications and marketplace metadata. The workflow covers data cleaning, preprocessing, model evaluation, hyperparameter tuning, and building an interactive user-input price prediction system.

---

## 📂 Dataset & Features

The dataset contains laptop listings with attributes such as:

* Laptop name & processor
* RAM & storage type
* Operating system
* Display size (in inches)
* Rating
* Number of ratings
* Number of reviews
* **Target variable — Price (₹)**

---

## 🧹 Data Cleaning

* Removed unused / redundant columns
* Standardized text fields to maintain consistency
* Handled missing values in:

  * rating
  * number of ratings
  * number of reviews
    → Filled using **mean imputation**

---

## ⚙️ Feature Preprocessing

* Separated the target variable (`price (in Rs.)`)
* Applied Label Encoding to categorical features
* Scaled numerical features using `StandardScaler`
* Performed **train–test split** before model evaluation

---

## 🧪 Model Training & Cross-Validation

Evaluated multiple regression models using 5-fold cross-validation:

| Model                 | R² Score   |
| --------------------- | ---------- |
| Linear Regression     | 26.24%     |
| Decision Tree         | 66.73%     |
| KNN                   | 55.47%     |
| AdaBoost              | 58.76%     |
| **Random Forest**     | **78.88%** |
| **Gradient Boosting** | **80.64%** |
| **XGBoost**           | **81.43%** |
| SVM                   | −11.47%    |

**Shortlisted Top 3 Models**

* Random Forest — 78.88%
* Gradient Boost — 80.73%
* XGBoost — 81.43%

---

## 🔧 Hyperparameter Tuning (GridSearchCV)

### Gradient Boosting

```
{ learning_rate: 0.15, max_depth: 3 }
CV Score: 0.8343
```

### Random Forest

```
{ max_depth: 14, max_features: 3 }
CV Score: 0.8200
```

---

## 🏁 Final Model Performance (Test Set)

| Model                 | Test R²    |
| --------------------- | ---------- |
| **Gradient Boosting** | **86.54%** |
| Random Forest         | 85.73%     |

🎯 **Final Model Selected:** `GradientBoostingRegressor`

---

## 💻 Interactive Prediction System

Built a user-input interface where users can enter laptop specifications including:

* Processor
* RAM
* Operating system
* Storage type
* Display size
* Rating
* Number of ratings / reviews

The trained model returns an estimated **laptop price (₹)**.

---

## 🛠️ Tech Stack

* Python • NumPy • Pandas
* Scikit-Learn
* XGBoost
* Matplotlib / Seaborn

---

## 🚀 Future Enhancements

* Replace label encoding with One-Hot Encoding
* Move preprocessing into a sklearn `Pipeline`
* Improve feature engineering
* Deploy model using Streamlit / Flask

---


