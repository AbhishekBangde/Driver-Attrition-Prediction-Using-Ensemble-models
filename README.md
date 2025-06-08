# Driver-Attrition-Prediction-Using-Ensemble-models

---

## 🏢 About OLA

**Ola**, one of India’s largest ride-hailing platforms, is facing significant challenges in **driver attrition and retention**. As it scales, maintaining a reliable pool of drivers is crucial. Hiring new drivers incurs high acquisition costs, whereas **retaining drivers through data-driven insights** can improve operational stability and customer satisfaction. This project aims to leverage **machine learning** to predict driver attrition based on performance, demographics, and historical behavior.

---

## 📁 Project Files

- **OLA - Ensemble Learning.ipynb**: Jupyter Notebook containing EDA, feature engineering, model building with Random Forest & Gradient Boosting, and final evaluation.
- **read_me.md**: Project overview, data understanding, methodology, and business insights.

---

## 🎯 Objective

To build a **binary classification model** using **ensemble learning techniques** to predict whether a driver is likely to leave Ola. The project helps Ola take **proactive retention actions**, optimize resources, and enhance workforce stability using historical data on demographics, performance, income trends, and designations.

---

## 🧾 Feature Details

The dataset consists of **2,381 driver records** (aggregated monthly) with the following key features:

### 🔹 Driver Demographics
- `Driver_ID`: Unique driver identifier
- `Age`: Driver’s age
- `Gender`: Male/Female (encoded)
- `City`: Operating city
- `Education_Level`: 0 = 10+, 1 = 12+, 2 = Graduate

### 🔹 Job & Designation
- `Joining Designation`: Entry-level designation at joining
- `Grade`: Driver’s internal performance grade
- `Dateofjoining`, `LastWorkingDate`: Used to derive tenure and attrition

### 🔹 Performance & Rating
- `Quarterly Rating`: Ratings over time (1 to 5)
- `rating_increased`: Flag if rating improved over time
- `avg_rating`: Average rating over entire tenure

### 🔹 Business Value & Income
- `Total Business Value`: Monthly value generated (refunded/cancelled handled)
- `Income`: Income records over time
- `income_increased`: Flag if income increased
- `avg_income`: Mean monthly income

### 🔹 Engineered Temporal Features
- `Year_of_joining`, `Month_of_joining`, `Day_of_joining`: Derived from joining date
- `Target`: **Target variable** (1 = Attrited, 0 = Retained)

---

## 🛠 Tools & Libraries Used

- **Python Libraries**: `pandas`, `numpy`, `matplotlib`, `seaborn`, `warnings`
- **Preprocessing**: `KNNImputer`, `StandardScaler`, `pd.get_dummies`, feature aggregation
- **Modeling**:
  - **Random Forest Classifier** (Bagging)
  - **Gradient Boosting Classifier** (Boosting)
- **Class Imbalance**: `SMOTE` from `imblearn`
- **Model Evaluation**: `accuracy_score`, `classification_report`, `roc_auc_score`, `roc_curve`

---

## 🌟 Key Highlights

- 🔍 **Extensive EDA**: Histograms, countplots, and correlation heatmaps for univariate and bivariate insights.
- 🧱 **Feature Engineering**: Created aggregated fields like `avg_income`, `rating_increased`, and tenure-based fields.
- ⚖️ **Class Imbalance Handling**: Balanced the attrition vs. retention labels using **SMOTE**.
- 🌲 **Model Performance**:
  - **Random Forest**: Accuracy = **86.37%**, ROC AUC = **0.917**
  - **Gradient Boosting**: Accuracy = **86.58%**, ROC AUC = **0.912**
  - Key features: `avg_rating`, `Year_of_joining`, `rating_increased`
- 📊 **Visualization**: ROC curves plotted to compare both ensemble models.

---

## ✅ Conclusion

This project builds **robust ensemble models** to predict **driver attrition**, a critical business problem for OLA. The models demonstrate high accuracy and discriminative power (AUC > 0.91), helping the company:

- Reduce retention costs by identifying drivers at risk early
- Improve performance via coaching and incentive plans
- Tailor city-specific and tenure-based interventions

By focusing on **high recall**, Ola can avoid false negatives and maximize retention strategies. **Random Forest** and **Gradient Boosting** both perform well, with Random Forest slightly outperforming in ROC comparison.

---
