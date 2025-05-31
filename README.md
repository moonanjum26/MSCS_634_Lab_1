# MSCS 634 – Lab 1: Data Preprocessing and Visualization

**Student**: Junaid Khan  
**Course**: MSCS 634 – Data Science Fundamentals  
**Lab Title**: Warehouse and Retail Sales Data Analysis

---

## 📌 Objective

This lab focuses on applying data visualization, data preprocessing, and statistical analysis techniques using Python (Pandas, Matplotlib, Seaborn) in Jupyter Notebook. The main goal is to clean and prepare a real-world dataset for deeper analytical tasks by identifying trends, handling anomalies, and understanding the underlying statistical structure.

---

## 🧾 Dataset

**Name**: Warehouse_and_Retail_Sales.csv  
**Source**: [Custom Upload / Provided]  
**Size**: 307,645 records × 9 columns  
**Fields Include**:
- YEAR, MONTH  
- SUPPLIER, ITEM CODE, ITEM DESCRIPTION, ITEM TYPE  
- RETAIL SALES, RETAIL TRANSFERS, WAREHOUSE SALES  

---

## 🧪 Steps Performed

### 🔹 Step 1: Data Collection
- Loaded the dataset using `pandas.read_csv()`.
- Displayed first 5 rows to understand structure.
- Verified null values and datatypes using `.info()` and `.describe()`.

### 🔹 Step 2: Data Visualization
- **Scatter Plot**: YEAR vs WAREHOUSE SALES with ITEM TYPE as hue → Showed sales trends across item categories over time.
- **Histogram**: Frequency distribution of records across years → Highlighted that 2019 had the highest number of entries.
- Described insights for each plot and what they reveal.

### 🔹 Step 3: Data Preprocessing
- **Missing Values**: Detected in `SUPPLIER`, `ITEM TYPE`, and `RETAIL SALES`; handled using `.dropna()` or `.fillna()`.
- **Outlier Detection**: Used IQR method on `WAREHOUSE SALES` → Outliers removed based on 1.5×IQR bounds.
- **Data Reduction**:
  - Sampled 30% of dataset using `.sample(frac=0.3)`
  - Dropped columns like `SUPPLIER`, `ITEM CODE`, `ITEM DESCRIPTION` to reduce dimensions.
- **Data Scaling**:
  - Used Min-Max Normalization for `WAREHOUSE SALES`.
- **Discretization**:
  - Binned `WAREHOUSE SALES` into 3 categories: Low, Medium, High.

### 🔹 Step 4: Statistical Analysis
- **General Overview**: `.info()` and `.describe()` to summarize dataset.
- **Central Tendency**: Computed min, max, mean, median, mode for `WAREHOUSE SALES`.
- **Dispersion**: Calculated range, quartiles, IQR, variance, and std deviation.
- **Correlation Analysis**: Heatmap using `.corr()` to show relationships between `RETAIL SALES`, `RETAIL TRANSFERS`, and `WAREHOUSE SALES`.

---

## 📊 Key Insights

- **Sales Pattern**: Alcoholic items like `WINE` and `LIQUOR` dominated warehouse sales consistently across years.
- **Skewness**: Both `RETAIL SALES` and `WAREHOUSE SALES` had a right-skewed distribution with some extreme outliers.
- **Data Imbalance**: Year-wise entries were uneven, with 2019 having the highest number of records.
- **Correlation**: Retail and warehouse sales showed mild to moderate positive correlation, suggesting potential predictive relationships.

---

## ⚠️ Challenges Faced

- Large data size slowed down some computations → resolved using `.sample()` for reduction.
- Some features had extreme negative or high outlier values → handled using IQR method.
- Deciding on scaling method and bin count for discretization required experimentation.

---

## 🗂️ Repository Structure

