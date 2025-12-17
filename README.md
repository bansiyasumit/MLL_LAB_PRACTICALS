
**Student Roll No:** `25901337`
**Course:** Machine Learning Lab
**Language:** Python
**Environment:** Google Colab / Jupyter Notebook

---

## 📁 Repository Structure

```text
StudentRollNo_##/
│
├── easy.ipynb        # Logistic Regression (Baseline)
├── moderate.ipynb    # Linear SVM with Hyperparameter Tuning
├── hard.ipynb        # KNN vs Linear SVM Comparison
│
├── README.md
├── requirements.txt
```

---

## 📊 Dataset Used

**DS5 – Telco Customer Churn Dataset**
Link: [https://www.kaggle.com/datasets/blastchar/telco-customer-churn](https://www.kaggle.com/datasets/blastchar/telco-customer-churn)

The dataset contains customer demographics, service usage, and billing details, with a binary target variable **`Churn`** indicating whether a customer leaves the service.

---

# 🟢 Practical 1 – EASY

## Logistic Regression (Baseline Model)

### 🎯 Objective

To build a **baseline binary classification model** using **Logistic Regression** to predict customer churn and evaluate it using the **ROC-AUC** metric.

### 🧪 Methodology

* Performed basic EDA: dataset shape, missing values, and target distribution
* Visualized churn distribution and monthly charges
* Encoded target variable (`Churn`: Yes → 1, No → 0)
* Applied one-hot encoding to categorical features
* Scaled features using StandardScaler
* Split data into training and validation sets
* Trained a Logistic Regression model

### 📈 Evaluation Metric

* **ROC-AUC Score**

### 🧠 Reasoning

Logistic Regression was chosen as a simple and interpretable baseline model. ROC-AUC was used as it evaluates performance across all classification thresholds and is suitable for imbalanced datasets.

---

# 🟡 Practical 2 – MODERATE

## Linear Support Vector Machine (SVM)

### 🎯 Objective

To build a **Linear SVM classifier**, tune hyperparameters **`C`** and **`class_weight`**, and evaluate the model using the **F1-score**.

### 🧪 Methodology

* Reused DS5 dataset with fresh preprocessing
* Conducted EDA and visualizations
* Applied one-hot encoding, creating a high-dimensional feature space
* Scaled features (mandatory for SVM)
* Used **GridSearchCV** to tune:

  * `C` (regularization strength)
  * `class_weight` (to handle class imbalance)
* Selected best model based on F1-score

### 📈 Evaluation Metric

* **F1-Score**

### 🧠 Reasoning

Linear SVM performs well in high-dimensional spaces. Hyperparameter tuning improves margin control and class balance handling. F1-score was chosen because it balances precision and recall in imbalanced classification problems.

---

# 🔴 Practical 3 – HARD

## KNN vs Linear SVM on Sparse High-Dimensional Data

### 🎯 Objective

To compare **KNN** and **Linear SVM** after one-hot encoding and analyze why **KNN struggles** in high-dimensional sparse feature spaces.

### 🧪 Methodology

* Used DS5 dataset and applied one-hot encoding
* Created a **high-dimensional sparse feature space**
* Scaled features for fair comparison
* Trained:

  * **KNN (distance-based classifier)**
  * **Linear SVM (margin-based classifier)**
* Evaluated both models using **F1-score**

### 📈 Results

* **KNN F1-score:** ≈ 0.51
* **Linear SVM F1-score:** ≈ 0.59

### 🧠 Analysis & Discussion

KNN relies on distance calculations, which become unreliable in high-dimensional sparse spaces due to the **curse of dimensionality**. As dimensions increase, distances between points become similar, reducing neighborhood quality. Linear SVM performs better because it focuses on learning an optimal separating hyperplane rather than relying on distance metrics, making it more robust to sparsity.

---

## ✅ Conclusion

* Logistic Regression provides a strong baseline
* Linear SVM outperforms the baseline after tuning
* Linear SVM significantly outperforms KNN in sparse, high-dimensional feature spaces

