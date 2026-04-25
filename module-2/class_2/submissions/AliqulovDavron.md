# 🛒 Superstore Data Preparation & Analysis (Python + Pandas)

This project demonstrates a complete **data preprocessing workflow** using the Superstore dataset.
It covers data loading, cleaning, transformation, and feature engineering — essential steps for any Data Science or Machine Learning project.

🔗 **Open in Google Colab:**
https://colab.research.google.com/drive/1n76XtrbeajgAw4aKxaJRwRellXoziWwk?usp=sharing

---

## 📌 Project Workflow

### 1. Load Dataset

```python
import kagglehub

path = kagglehub.dataset_download("vivek468/superstore-dataset-final")
print("Path to dataset files:", path)

url = '/kaggle/input/superstore-dataset-final/Sample - Superstore.csv'
```

---

### 2. Import Data

```python
import pandas as pd

df = pd.read_csv(url, encoding='cp1252')
df.head(10)
```

---

### 3. Inspect Data Structure

```python
print("Shape:", df.shape)
df.info()
df.describe()
```

✔️ Understand:

* Number of rows & columns
* Data types
* Missing values
* Statistical summary

---

### 4. Handle Missing Values

```python
print(df.isnull().sum())

df['Sales'].fillna(df['Sales'].median(), inplace=True)
df['Ship Mode'].fillna(df['Ship Mode'].mode()[0], inplace=True)

print(df.isnull().sum())
```

✔️ Strategy:

* Numerical → Median
* Categorical → Mode

---

### 5. Remove Duplicates

```python
print("Duplicate rows:", df.duplicated().sum())

df = df.drop_duplicates()
print("Shape after removing duplicates:", df.shape)
```

---

### 6. Convert Data Types

```python
df['Order Date'] = pd.to_datetime(df['Order Date'])
df['Ship Date'] = pd.to_datetime(df['Ship Date'])

print(df.dtypes)
df[['Order Date', 'Ship Date']].head()
```

---

### 7. Feature Engineering (Customer Analytics)

#### 💰 Total Spending per Customer

```python
total_spending = df.groupby('Customer ID')['Sales'].sum().reset_index()
```

#### 📦 Order Frequency

```python
order_freq = df.groupby('Customer ID')['Order ID'].nunique().reset_index()
```

#### 📊 Average Order Value

```python
avg_order = df.groupby('Customer ID')['Sales'].mean().reset_index()
```

---

### 8. Merge Features

```python
customer_summary = total_spending.merge(order_freq, on='Customer ID') \
                                 .merge(avg_order, on='Customer ID')

customer_summary.head(10)
```

---

### 9. Save Cleaned Data

```python
df.to_csv('superstore_cleaned.csv', index=False)
customer_summary.to_csv('customer_summary.csv', index=False)
```

---

## 🎯 Key Learning Outcomes

* Data cleaning techniques
* Handling missing values properly
* Removing duplicates
* Working with datetime data
* GroupBy operations in Pandas
* Feature engineering for customer analysis

---

## 🚀 Use Cases

This processed dataset can be used for:

* Customer segmentation
* Sales prediction
* Business analytics dashboards
* Machine Learning models

---

## 🛠️ Tech Stack

* Python 🐍
* Pandas 📊
* KaggleHub

---

## 👨‍💻 Author

**Davron Aliqulov**
AI & Data Science Learner 🚀

---

## 📚 Next Steps

* Visualize data (Matplotlib / Seaborn)
* Build ML models (Regression / Classification)
* Perform customer segmentation (Clustering)

---
