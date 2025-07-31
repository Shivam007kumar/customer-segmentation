# 🧮 PySpark Transaction Data Analysis

**Project Objective**  
This project performs a large-scale analysis of customer transaction data using Apache Spark's Python API, **PySpark**. It processes, cleans, and analyzes over **13 million transactions** to uncover patterns in consumer behavior, geographic trends, and transaction errors.

---

## 📊 Key Features

- **Big Data Processing**: Handles 13.3M+ records using distributed computing with PySpark.
- **Data Cleaning & Preprocessing**: Cleans currency strings and casts to numeric types.
- **Feature Engineering**: Maps MCC codes to readable category labels using a JSON lookup.
- **Comprehensive Analysis**:
  - Spending by Category
  - Monthly Transaction Trends
  - Spending by State
  - Top Performing Merchants
  - Transaction Error Analysis
- **Data Visualization**:
  - Static charts using `matplotlib`
  - Interactive dashboards using `plotly`
- **Exportable Results**: Outputs summaries to `.csv` and plots to `.html` files.

---

## ⚙️ Project Pipeline

1. **Initialization**  
   A `SparkSession` is created with the name `"Customer Segmentation"`.

2. **Data Loading**  
   Loads `transactions_data.csv` into a Spark DataFrame with header and schema inference.

3. **Exploratory Data Analysis (EDA)**  
   Uses `.count()`, `.printSchema()`, and `.describe()` to understand data.

4. **Data Preprocessing**  
   Cleans the `amount` column (e.g., removes `$`, `,`) and casts it to float.

5. **Feature Engineering**  
   - Loads `mcc_codes.json` for mapping MCC codes.
   - Creates a UDF to generate a new `category` column.

6. **Aggregation & Analysis**
   - **Category Summary**: Count, sum, and average by category.
   - **Monthly Summary**: Trends over year and month.
   - **State Summary**: Transaction volume/value by state.
   - **Merchant Summary**: Top 10 merchants by spend.
   - **Error Summary**: Frequency of different error types.

7. **Visualization & Exporting**
   - Converts aggregated Spark DataFrames to Pandas.
   - Creates:
     - Static charts with `matplotlib`
     - Interactive charts with `plotly`
   - Exports:
     - `.csv` summary files
     - `.html` interactive plots

---

## 📋 Requirements

To run this project, install the following:

```bash
pip install pyspark matplotlib plotly pandas