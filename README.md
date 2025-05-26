# 🧼 Titanic Dataset Preprocessing Guide

This repository contains a mini-guide and code snippets for performing essential **data preprocessing** tasks on the Titanic dataset. It covers key steps such as handling missing values, encoding categorical features, standardizing data, and identifying outliers.

---

## 📁 Dataset

The dataset used is the classic [Titanic dataset](https://www.kaggle.com/competitions/titanic/data), which includes information about passengers on the Titanic and whether they survived.

---

## 🛠️ Preprocessing Steps

### 1. Importing and Exploring the Dataset
We begin by importing the dataset using `pandas` and exploring its structure using `.info()`, `.isnull().sum()`, and `.head()`. This helps us understand the data types, missing values, and general shape of the data.

### 2. Handling Missing Values
Missing values are handled using strategies like:
- Filling numerical features (`Age`) with the **median**.
- Filling categorical features (`Embarked`) with the **mode**.
- Dropping columns (`Cabin`) if too many values are missing.

This step ensures the dataset is clean and ready for analysis.

### 3. Encoding Categorical Features
Machine learning models work with numerical data, so we convert categorical features:
- `Sex` and `Embarked` are encoded using **one-hot encoding** (with `drop_first=True` to avoid multicollinearity).
This step makes the dataset model-compatible.

### 4. Standardizing Numerical Features
To bring all numerical features to a common scale:
- We use `StandardScaler` to standardize features like `Age` and `Fare` to have zero mean and unit variance.
This improves performance of models that are sensitive to feature scaling.

### 5. Visualizing and Removing Outliers
Outliers are detected using **boxplots**:
- Outliers in features like `Fare` are removed using the **Interquartile Range (IQR)** method to prevent skewed results and improve model performance.

---

## 📦 Dependencies

Install the following Python libraries before running the scripts:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn
