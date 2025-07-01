# Data Pipeline Lab: ETL for Sales Transactions

**Student Name**: Faith Chakwanira
**Student ID**: 670435
**Submission Date**: June 10, 2025

## 🎯 Project Goal

This project showcases fundamental Extract-Transform-Load (ETL) techniques, specifically focusing on **Full Data Extraction** and **Incremental Updates**. Using Python and Jupyter Notebooks, it simulates a real-world data pipeline by processing synthetic sales transaction data. The primary goal is to demonstrate efficient methods for data ingestion, whether it's an initial complete dataset load or capturing only new/modified records since the last processing run.

## 🔑 Key Concepts & Demonstrations

### 1. Full Extraction

This module illustrates how to perform a complete load of a dataset from its source. Essential for initial setup or periodic full refreshes, this process ensures all available data is captured. The accompanying notebook clearly displays statistical summaries and a data sample to confirm successful execution.

### 2. Incremental Extraction

A more efficient approach for dynamic datasets, incremental extraction focuses on identifying and retrieving only data that has been newly added or updated since the last ETL run. This significantly optimizes performance and resource usage for frequently changing data sources. The simulation within this project demonstrates how new sales records are seamlessly integrated via this method.

### 3. Data Simulation & State Management

To provide a realistic scenario, the project includes:
*   **Synthetic Data Generation**: A `custom_data.csv` file is created with over 50 realistic sales transactions, incorporating `transaction_date` and `last_updated` timestamps crucial for incremental logic.
*   **Persistent Timestamp Tracking**: A `last_extraction.txt` file is used to store the timestamp of the most recent successful incremental extraction. This mechanism simulates a real-world persistent state, allowing the ETL process to know where to resume.

## ⚙️ Technologies Utilized

*   **Python 3**: The core language for scripting the ETL logic.
*   **Pandas**: Employed for robust data manipulation, analysis, and efficient handling of DataFrames.
*   **Jupyter Notebook**: Provides an interactive environment for developing, documenting, and executing the ETL workflow.
*   **Git/GitHub**: For version control, project tracking, and collaborative development.

## 📂 Project Repository Overview

```
ETL_Extract_Faithchakwanira_670435/
├── etl_extract.ipynb         # Main Jupyter notebook containing all ETL operations
├── custom_data.csv           # Generated synthetic sales dataset
├── last_extraction.txt       # Stores the timestamp for incremental data pulls
├── .gitignore                # Specifies files to exclude from version control
├── README.md                 # This project documentation
├── image.png                 # Screenshot: Data Generation Output
├── image-1.png               # Screenshot: Full Extraction Output
├── image-2.png               # Screenshot: Incremental Extraction Output
└── image-3.png               # Screenshot: Simulate New Data for Incremental Extraction
```

## 🚀 Quick Start Guide

Follow these steps to set up and run the ETL pipeline on your local system:

### Prerequisites

Ensure you have Python 3 installed. Then, install the necessary libraries using pip:

```bash
pip install pandas jupyter
```

### Data Handling

The `custom_data.csv` file is **automatically generated** when you execute the first cell of the `etl_extract.ipynb` notebook. No manual download is required.

### Getting the Code

Clone this repository to your local machine:

```bash
https://github.com/fai-alt/ETL_Extract_Faithchakwanira_670435.git
cd ETL_Extract_Faithchakwanira_670435
```

### Running the Notebook

1.  Launch Jupyter Notebook from your project directory:
    ```bash
    jupyter notebook
    ```
2.  In the Jupyter interface, open `etl_extract.ipynb`.
3.  Execute all cells in sequence (via `Cell` -> `Run All`) to observe the full ETL process.

## 📊 Visualizing the Process

The `etl_extract.ipynb` notebook provides clear outputs at each stage of the ETL process. Here's a textual representation of what the various outputs demonstrate:

### 1. Data Generation Output: Sales Data Sample

This section illustrates the initial synthetic sales dataset, `custom_data.csv`, which contains 100 records.

**Sample Data (First 5 Rows):**

```
| transaction_id | customer_id | product_id | product_name      | category      | quantity | unit_price | amount  | transaction_date      | last_updated          | payment_method | region |
|----------------|-------------|------------|-------------------|---------------|----------|------------|---------|-----------------------|-----------------------|----------------|--------|
| 10000          | 1114        | F606       | Screen Protector  | Accessories   | 1        | 13.62      | 13.62   | 2025-04-26 17:56:10  | 2025-04-27 07:56:10  | Debit Card     | North  |
| 10001          | 1758        | F606       | Screen Protector  | Accessories   | 3        | 11.92      | 35.76   | 2025-05-08 17:56:10  | 2025-05-08 19:56:10  | Credit Card    | North  |
| 10002          | 1238        | B202       | Bluetooth Speaker | Electronics   | 3        | 51.01      | 153.03  | 2025-05-16 17:56:10  | 2025-05-17 05:56:10  | Cash           | South  |
| 10003          | 1603        | D404       | Phone Case        | Accessories   | 2        | 21.23      | 42.46   | 2025-04-11 17:56:10  | 2025-04-13 17:56:10  | Debit Card     | West   |
| 10004          | 1284        | C303       | Smart Watch       | Electronics   | 1        | 188.60     | 188.60  | 2025-05-29 17:56:10  | 2025-05-30 14:56:10  | Credit Card    | North  |
```

### 2. Full Extraction Output

This output confirms a full extraction of all 100 records from `custom_data.csv`.

**Extracted Columns:** `transaction_id`, `customer_id`, `product_id`, `product_name`, `category`, `quantity`, `unit_price`, `amount`, `transaction_date`, `last_updated`, `payment_method`, `region`

**Sample Rows (First 3):**

```
| 10000 | 1114 | F606 | Screen Protector  | Accessories | 1 | 13.62  | 13.62  | 2025-04-26 17:41:59 | 2025-04-27 07:41:59 | Debit Card  | North |
| 10001 | 1758 | F606 | Screen Protector  | Accessories | 3 | 11.92  | 35.76  | 2025-05-08 17:41:59 | 2025-05-08 19:41:59 | Credit Card | North |
| 10002 | 1238 | B202 | Bluetooth Speaker | Electronics | 3 | 51.01  | 153.03 | 2025-05-16 17:41:59 | 2025-05-17 05:41:59 | Cash        | South |
```

**Last 5 Rows:**

```
| 10095 | 1249 | D404 | Phone Case         | Accessories | 2 | 20.27  | 40.54  | 2025-05-23 17:41:59 | 2025-05-24 17:41:59 | PayPal      | North |
| 10096 | 1871 | D404 | Phone Case         | Accessories | 2 | 18.72  | 37.44  | 2025-04-24 17:41:59 | 2025-04-25 15:41:59 | PayPal      | East  |
| 10097 | 1901 | C303 | Smart Watch        | Electronics | 3 | 208.04 | 624.12 | 2025-04-28 17:41:59 | 2025-04-30 04:41:59 | Credit Card | South |
| 10098 | 1247 | A101 | Wireless Headphones| Electronics | 3 | 88.31  | 264.93 | 2025-05-16 17:41:59 | 2025-05-18 17:41:59 | Debit Card  | West  |
| 10099 | 1728 | F606 | Screen Protector   | Accessories | 2 | 12.86  | 25.72  | 2025-04-12 17:41:59 | 2025-04-12 22:41:59 | PayPal      | South |
```

### 3. Incremental Extraction Output

This output demonstrates the incremental extraction process, showing only new or updated records since the last run.

**Last Extraction Timestamp:** 2025-06-10 18:10:11.510752
**New/Updated Records:** 1
```
| transaction_id | customer_id | product_id | product_name | category    | quantity | unit_price | amount | transaction_date      | last_updated          | payment_method | region |
|----------------|-------------|------------|--------------|-------------|----------|------------|--------|-----------------------|-----------------------|----------------|--------|
| 10009          | 1214        | C303       | Smart Watch  | Electronics | 3        | 190.67     | 572.01 | 2025-06-09 17:41:59   | 2025-06-11 12:41:59  | Credit Card    | South  |
```

### 4. Simulated New Records for Incremental Update

This section shows the details of new transactions added to the dataset to simulate new data arrivals for an incremental run.

**Status:** Added 3 new transactions

**New Records Details:**

1.  **Transaction ID**: 10100
    **Customer ID**: 1708
    **Product ID**: D404
    **Product Name**: Phone Case
    **Category**: Accessories
    **Quantity**: 1
    **Unit Price**: 19.22
    **Amount**: 19.22
    **Transaction Date**: 2025-06-08 18:19:09
    **Last Updated**: 2025-06-10 18:19:09
    **Payment Method**: Debit
    **Region**: West

2.  **Transaction ID**: 10100
    **Customer ID**: 1543
    **Product ID**: E505
    **Product Name**: USB Cable
    **Category**: Accessories
    **Quantity**: 2
    **Unit Price**: 9.84
    **Amount**: 19.68
    **Transaction Date**: 2025-06-08 18:19:09
    **Last Updated**: 2025-06-10 18:19:09
    **Payment Method**: PayPal
    **Region**: East

3.  **Transaction ID**: 10100
    **Customer ID**: 1719
    **Product ID**: C303 (originally 303, fixed)
    **Product Name**: Smart Watch
    **Category**: Electronics
    **Quantity**: 2
    **Unit Price**: 190.83
    **Amount**: 381.66
    **Transaction Date**: 2025-06-09 18:19:09
    **Last Updated**: 2025-06-10 18:19:09
    **Payment Method**: Credit
    **Region**: North

## ✨ Final Thoughts

This project effectively demonstrates both comprehensive and incremental data extraction methodologies, vital for building efficient and scalable data pipelines. The detailed explanations and practical demonstrations within the notebook and this README aim to provide a thorough understanding of these concepts.

## Lab 4 – Transform

**Transformations applied:**
1. **Cleaning:** Removed duplicate rows and filled missing values in the `quantity` column with 0.
2. **Enrichment:** Added a new column `total_price` calculated as `quantity * unit_price`.
3. **Structural:** Standardized the `transaction_date` column to the format `YYYY-MM-DD`.

**Transformed files produced:**
- `transformed_full.csv` – the fully transformed dataset.
- `transformed_incremental.csv` – the last 10 rows of the transformed dataset, simulating incremental data.

---

## Lab 5 – Load

**Loading methods used:**
- **Parquet:** Saved the transformed data as columnar Parquet files for efficient storage and analytics.
- **SQLite:** Loaded the transformed data into SQLite databases for structured querying.

**Sample loading code:**
```python
import pandas as pd
import sqlite3

# Load transformed CSV
df = pd.read_csv('transformed_full.csv')

# Save as Parquet
df.to_parquet('loaded_data/full_data.parquet')

# Save to SQLite
with sqlite3.connect('loaded_data/full_data.db') as conn:
    df.to_sql('full_data', conn, if_exists='replace', index=False)
```

**Output locations:**
- Parquet: `loaded_data/full_data.parquet`, `loaded_data/incremental_data.parquet`
- SQLite: `loaded_data/full_data.db`, `loaded_data/incremental_data.db`

**Verification:**
- Parquet and SQLite files were loaded and previewed in the notebook to confirm successful loading.

---

## Output Samples and Explanation

### 1. First 5 Rows of Transformed Full Data
This table shows the first five rows of the fully transformed dataset (`transformed_full.csv`). It demonstrates the cleaned, enriched, and structured data, including the new `total_price` column and standardized `transaction_date`.

<!-- First 5 rows of full data -->
<div>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>transaction_id</th>
      <th>customer_id</th>
      <th>product_id</th>
      <th>product_name</th>
      <th>category</th>
      <th>quantity</th>
      <th>unit_price</th>
      <th>amount</th>
      <th>transaction_date</th>
      <th>last_updated</th>
      <th>payment_method</th>
      <th>region</th>
      <th>total_price</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>10000</td>
      <td>1114</td>
      <td>F606</td>
      <td>Screen Protector</td>
      <td>Accessories</td>
      <td>1</td>
      <td>13.62</td>
      <td>13.62</td>
      <td>2025-04-26</td>
      <td>2025-04-27 07:41:59</td>
      <td>Debit Card</td>
      <td>North</td>
      <td>13.62</td>
    </tr>
    <tr>
      <th>1</th>
      <td>10001</td>
      <td>1758</td>
      <td>F606</td>
      <td>Screen Protector</td>
      <td>Accessories</td>
      <td>3</td>
      <td>11.92</td>
      <td>35.76</td>
      <td>2025-05-08</td>
      <td>2025-05-08 19:41:59</td>
      <td>Credit Card</td>
      <td>North</td>
      <td>35.76</td>
    </tr>
    <tr>
      <th>2</th>
      <td>10002</td>
      <td>1238</td>
      <td>B202</td>
      <td>Bluetooth Speaker</td>
      <td>Electronics</td>
      <td>3</td>
      <td>51.01</td>
      <td>153.03</td>
      <td>2025-05-16</td>
      <td>2025-05-17 05:41:59</td>
      <td>Cash</td>
      <td>South</td>
      <td>153.03</td>
    </tr>
    <tr>
      <th>3</th>
      <td>10003</td>
      <td>1603</td>
      <td>D404</td>
      <td>Phone Case</td>
      <td>Accessories</td>
      <td>2</td>
      <td>21.23</td>
      <td>42.46</td>
      <td>2025-04-11</td>
      <td>2025-04-13 17:41:59</td>
      <td>Debit Card</td>
      <td>West</td>
      <td>42.46</td>
    </tr>
    <tr>
      <th>4</th>
      <td>10004</td>
      <td>1284</td>
      <td>C303</td>
      <td>Smart Watch</td>
      <td>Electronics</td>
      <td>1</td>
      <td>188.60</td>
      <td>188.60</td>
      <td>2025-05-29</td>
      <td>2025-05-30 14:41:59</td>
      <td>Credit Card</td>
      <td>North</td>
      <td>188.60</td>
    </tr>
  </tbody>
</table>
</div>

### 2. Last 5 Rows of Transformed Full Data
This table shows the last five rows of the fully transformed dataset, demonstrating the data at the end of the file, including any new or updated records.

<!-- Last 5 rows of full data -->
<div>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>transaction_id</th>
      <th>customer_id</th>
      <th>product_id</th>
      <th>product_name</th>
      <th>category</th>
      <th>quantity</th>
      <th>unit_price</th>
      <th>amount</th>
      <th>transaction_date</th>
      <th>last_updated</th>
      <th>payment_method</th>
      <th>region</th>
      <th>total_price</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>10096</td>
      <td>1871</td>
      <td>D404</td>
      <td>Phone Case</td>
      <td>Accessories</td>
      <td>2</td>
      <td>18.72</td>
      <td>37.44</td>
      <td>2025-04-24</td>
      <td>2025-04-25 15:41:59</td>
      <td>PayPal</td>
      <td>East</td>
      <td>37.44</td>
    </tr>
    <tr>
      <th>1</th>
      <td>10097</td>
      <td>1901</td>
      <td>C303</td>
      <td>Smart Watch</td>
      <td>Electronics</td>
      <td>3</td>
      <td>208.04</td>
      <td>624.12</td>
      <td>2025-04-28</td>
      <td>2025-04-30 04:41:59</td>
      <td>Credit Card</td>
      <td>South</td>
      <td>624.12</td>
    </tr>
    <tr>
      <th>2</th>
      <td>10098</td>
      <td>1247</td>
      <td>A101</td>
      <td>Wireless Headphones</td>
      <td>Electronics</td>
      <td>3</td>
      <td>88.31</td>
      <td>264.93</td>
      <td>2025-05-16</td>
      <td>2025-05-18 17:41:59</td>
      <td>Debit Card</td>
      <td>West</td>
      <td>264.93</td>
    </tr>
    <tr>
      <th>3</th>
      <td>10099</td>
      <td>1728</td>
      <td>F606</td>
      <td>Screen Protector</td>
      <td>Accessories</td>
      <td>2</td>
      <td>12.86</td>
      <td>25.72</td>
      <td>2025-04-12</td>
      <td>2025-04-12 22:41:59</td>
      <td>PayPal</td>
      <td>South</td>
      <td>25.72</td>
    </tr>
    <tr>
      <th>4</th>
      <td>10100</td>
      <td>1708</td>
      <td>D404</td>
      <td>Phone Case</td>
      <td>Accessories</td>
      <td>1</td>
      <td>19.22</td>
      <td>19.22</td>
      <td>2025-06-08</td>
      <td>2025-06-10 18:19:09</td>
      <td>Debit</td>
      <td>West</td>
      <td>19.22</td>
    </tr>
  </tbody>
</table>
</div>

### 3. First 5 Rows of Transformed Incremental Data
This table shows the first five rows of the incremental dataset (`transformed_incremental.csv`), which contains the last 10 rows of the full transformed data. This simulates new or recently updated records for incremental loading.

<!-- First 5 rows of incremental data -->
<div>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>transaction_id</th>
      <th>customer_id</th>
      <th>product_id</th>
      <th>product_name</th>
      <th>category</th>
      <th>quantity</th>
      <th>unit_price</th>
      <th>amount</th>
      <th>transaction_date</th>
      <th>last_updated</th>
      <th>payment_method</th>
      <th>region</th>
      <th>total_price</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>10096</td>
      <td>1871</td>
      <td>D404</td>
      <td>Phone Case</td>
      <td>Accessories</td>
      <td>2</td>
      <td>18.72</td>
      <td>37.44</td>
      <td>2025-04-24</td>
      <td>2025-04-25 15:41:59</td>
      <td>PayPal</td>
      <td>East</td>
      <td>37.44</td>
    </tr>
    <tr>
      <th>1</th>
      <td>10097</td>
      <td>1901</td>
      <td>C303</td>
      <td>Smart Watch</td>
      <td>Electronics</td>
      <td>3</td>
      <td>208.04</td>
      <td>624.12</td>
      <td>2025-04-28</td>
      <td>2025-04-30 04:41:59</td>
      <td>Credit Card</td>
      <td>South</td>
      <td>624.12</td>
    </tr>
    <tr>
      <th>2</th>
      <td>10098</td>
      <td>1247</td>
      <td>A101</td>
      <td>Wireless Headphones</td>
      <td>Electronics</td>
      <td>3</td>
      <td>88.31</td>
      <td>264.93</td>
      <td>2025-05-16</td>
      <td>2025-05-18 17:41:59</td>
      <td>Debit Card</td>
      <td>West</td>
      <td>264.93</td>
    </tr>
    <tr>
      <th>3</th>
      <td>10099</td>
      <td>1728</td>
      <td>F606</td>
      <td>Screen Protector</td>
      <td>Accessories</td>
      <td>2</td>
      <td>12.86</td>
      <td>25.72</td>
      <td>2025-04-12</td>
      <td>2025-04-12 22:41:59</td>
      <td>PayPal</td>
      <td>South</td>
      <td>25.72</td>
    </tr>
    <tr>
      <th>4</th>
      <td>10100</td>
      <td>1708</td>
      <td>D404</td>
      <td>Phone Case</td>
      <td>Accessories</td>
      <td>1</td>
      <td>19.22</td>
      <td>19.22</td>
      <td>2025-06-08</td>
      <td>2025-06-10 18:19:09</td>
      <td>Debit</td>
      <td>West</td>
      <td>19.22</td>
    </tr>
  </tbody>
</table>
</div>


