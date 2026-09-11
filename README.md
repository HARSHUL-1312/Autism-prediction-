# 🧩 Autism Prediction Using Machine Learning

A Machine Learning project that predicts **Autism Spectrum Disorder (ASD)** based on screening scores and demographic information.

## 📌 Project Overview

The objective of this project is to build a classification model that predicts whether a person is likely to be classified as having ASD based on screening and demographic features.

The project includes:

* Data exploration and visualization
* Data cleaning and preprocessing
* Categorical feature encoding
* Outlier detection and handling
* Class imbalance handling using **SMOTE**
* Multiple machine learning models
* Hyperparameter tuning using **RandomizedSearchCV**
* Ensemble learning using a **Voting Classifier**
* Error analysis and visualization

## 📊 Dataset

The dataset contains **800 samples and 22 columns**.

The target variable is:

* `0` → No ASD
* `1` → ASD

The original dataset contains:

* **639 samples** in class 0
* **161 samples** in class 1

Because the target classes are imbalanced, **SMOTE** is applied to the training data. After resampling, both classes contain **515 samples**.

## 🧹 Data Preprocessing

The following preprocessing steps are performed:

* Convert age to integer
* Remove unnecessary columns such as `ID` and `age_desc`
* Standardize inconsistent country names
* Combine certain ethnicity and relation categories
* Encode categorical variables using `LabelEncoder`
* Detect and replace outliers in `age` and `result` using the median
* Handle class imbalance using **SMOTE**

## 🤖 Machine Learning Models

The project evaluates three classification algorithms:

* Decision Tree
* Random Forest
* XGBoost

Five-fold cross-validation is used during model evaluation.

Hyperparameter tuning is performed using **RandomizedSearchCV**.

### Best Cross-Validation Results

| Model         | Best CV Accuracy |
| ------------- | ---------------: |
| Decision Tree |           85.34% |
| Random Forest |       **92.33%** |
| XGBoost       |           91.17% |

The **Random Forest Classifier** achieved the best cross-validation accuracy of **92.33%**.

## 📈 Final Model Performance

The tuned Random Forest model achieved:

**Test Accuracy: 84.38%**

### Classification Report

| Class                | Precision | Recall | F1-Score |
| -------------------- | --------: | -----: | -------: |
| 0                    |      0.92 |   0.88 |     0.90 |
| 1                    |      0.63 |   0.72 |     0.68 |
| **Overall Accuracy** |           |        | **0.84** |

The model correctly classified **126 out of 160 test samples**, with **34 misclassified samples**.

## 🔬 Ensemble Learning

A **Soft Voting Classifier** was also implemented using the tuned Decision Tree, Random Forest, and XGBoost models.

The ensemble model achieved:

**Test Accuracy: 78.75%**

Since the ensemble performed worse than the tuned Random Forest model, the Random Forest model remains the stronger model in this experiment.

## 🔍 Error Analysis

The project analyzes incorrectly classified samples to identify potential patterns in prediction errors.

Visualizations are created to compare correct and incorrect predictions based on:

* Screening result
* Age

## 🛠️ Technologies Used

* Python
* NumPy
* Pandas
* Matplotlib
* Seaborn
* Scikit-learn
* XGBoost
* Imbalanced-learn
* SMOTE
* Google Colab

## 📂 Project Structure

```text
autism-prediction/
│
├── Autism_prediction.ipynb
├── encode.pkl
├── best_model.pkl
└── README.md
```

## ▶️ How to Run

1. Open the notebook in **Google Colab**.
2. Upload the required `train.csv` dataset.
3. Run the notebook cells sequentially.
4. The notebook will perform preprocessing, model training, hyperparameter tuning, evaluation, and error analysis.

## 🚀 Future Improvements

* Perform more extensive hyperparameter optimization
* Compare additional classification algorithms
* Evaluate ROC-AUC and precision-recall curves
* Investigate feature importance
* Improve handling of categorical variables
* Experiment with alternative approaches to class imbalance
* Deploy the trained model as a web application or API

## 👨‍💻 Author

**Harshul Sharma**
