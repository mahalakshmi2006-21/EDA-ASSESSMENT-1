# 📊 EDA Assessment 1 – Exploratory Data Analysis on Superstore Dataset

## 📌 Project Title

**Exploratory Data Analysis (EDA) on Superstore Dataset**

## 📖 Introduction

This project performs **Exploratory Data Analysis (EDA)** on the Superstore dataset. The main purpose of EDA is to understand the structure, characteristics, patterns, and important insights present in the dataset.

Python libraries such as **Pandas, NumPy, Matplotlib, and Seaborn** are used for data loading, data inspection, statistical analysis, data preprocessing, and visualization.

## 🎯 Objectives

The main objectives of this EDA project are:

* Load the Superstore dataset.
* Inspect the dataset structure.
* Understand rows and columns.
* Check data types.
* Generate descriptive statistics.
* Convert date columns into proper datetime format.
* Analyze sales based on product categories.
* Visualize category-wise sales using a bar chart.

## 🛠️ Technologies and Libraries Used

* **Python**
* **Jupyter Notebook / Google Colab**
* **Pandas** – Data manipulation and analysis
* **NumPy** – Numerical operations
* **Matplotlib** – Data visualization
* **Seaborn** – Statistical data visualization

## 📂 Dataset

The analysis is performed using the **Superstore dataset**.

The dataset contains information related to:

* Orders
* Customers
* Shipping
* Products
* Categories
* Sales
* Quantity
* Discount
* Profit
* Regions

### Dataset Size

* **Rows:** 10,194
* **Columns:** 21

## 🔍 EDA Operations Performed

### 1. Importing Libraries

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
```

These libraries are used for data analysis, numerical operations, and visualization.

### 2. Loading the Dataset

```python
df = pd.read_csv("/content/samplesuperstore.csv")
```

The Superstore CSV file is loaded into a Pandas DataFrame named `df`.

### 3. Displaying First Five Records

```python
df.head()
```

This displays the first five records of the dataset.

The records contain information such as:

* Row ID
* Order ID
* Order Date
* Ship Date
* Ship Mode
* Customer ID
* Customer Name
* Segment
* Country/Region
* City
* Category
* Sub-Category
* Product Name
* Sales
* Quantity
* Discount
* Profit

### 4. Displaying Last Five Records

```python
df.tail()
```

This displays the last five records of the dataset.

### 5. Checking Dataset Information

```python
df.info()
```

The dataset contains:

* **10,194 entries**
* **21 columns**
* **2 integer columns**
* **3 floating-point columns**
* **16 object/string columns**

Important numerical columns include:

* Sales
* Quantity
* Discount
* Profit

### 6. Checking Dataset Shape

```python
df.shape
```

**Output:**

```text
(10194, 21)
```

This means the dataset contains **10,194 rows and 21 columns**.

### 7. Descriptive Statistics

```python
df.describe()
```

The `describe()` function provides statistical information about the numerical columns.

| Column   |   Mean |    Minimum |   Maximum |
| -------- | -----: | ---------: | --------: |
| Sales    | 228.23 |      0.444 | 22,638.48 |
| Quantity |   3.79 |          1 |        14 |
| Discount |  0.155 |          0 |       0.8 |
| Profit   |  28.67 | -6,599.978 | 8,399.976 |

These statistics help understand the distribution and range of numerical values.

### 8. Converting Date Columns

```python
df['Order Date'] = pd.to_datetime(df['Order Date'], format='mixed')
df['Ship Date'] = pd.to_datetime(df['Ship Date'], format='mixed')
```

The `Order Date` and `Ship Date` columns are converted from string/object format into proper datetime format.

After conversion, both columns have the datatype:

```text
datetime64[ns]
```

### 9. Checking Data Types After Conversion

```python
df.info()
```

After preprocessing, the `Order Date` and `Ship Date` columns are correctly identified as datetime columns.

This makes the dataset suitable for future **time-based analysis**.

## 📊 Category-wise Sales Analysis

Total sales for each product category are calculated using the `groupby()` function.

```python
category_sales = df.groupby('Category')['Sales'].sum()
category_sales
```

### Output

| Category        |  Total Sales |
| --------------- | -----------: |
| Furniture       | 754,747.7613 |
| Office Supplies | 731,893.3140 |
| Technology      | 839,893.2790 |

## 📈 Data Visualization

A bar chart is created to visualize total sales by category.

```python
category_sales.plot(kind='bar', figsize=(8,5))
plt.title("Sales by Category")
plt.ylabel("Total Sales")
plt.show()
```

The bar chart visually compares the total sales of:

* Furniture
* Office Supplies
* Technology

This makes it easier to understand the differences in sales performance across categories.

## 🔎 Key Findings

From the EDA:

* The dataset contains **10,194 records and 21 columns**.
* It contains customer, order, product, sales, discount, and profit information.
* `Order Date` and `Ship Date` were converted into datetime format.
* The average sales value is approximately **228.23**.
* The average quantity is approximately **3.79**.
* The average profit is approximately **28.67**.
* Category-wise sales were calculated using `groupby()`.
* The three analyzed categories are **Furniture, Office Supplies, and Technology**.
* Category-wise sales were visualized using a **bar chart**.

## ✅ Conclusion

The EDA process helped in understanding the structure and characteristics of the Superstore dataset.

Basic **data inspection, statistical analysis, preprocessing, grouping, and visualization** were performed using Python.

The analysis provides a basic understanding of sales performance across different product categories and prepares the dataset for further analysis and visualization.

## 📁 Files Included

```text
EDA_ASSESMENT_1.ipynb
README.md
samplesuperstore.csv
```

## ▶️ How to Run

1. Open `EDA_ASSESMENT_1.ipynb` in **Jupyter Notebook** or **Google Colab**.
2. Upload the `samplesuperstore.csv` dataset.
3. Run the notebook cells in order.
4. View the generated outputs and visualizations.

## 📝 Submission Details

**Submitted as:** EDA Assessment 1
**Topic:** Exploratory Data Analysis on Superstore Dataset
