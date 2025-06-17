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
git clone [YOUR_REPOSITORY_URL_HERE] # Replace with your actual repository URL
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

The `etl_extract.ipynb` notebook includes clear outputs at each stage. Below are illustrative screenshots:

### Data Generation and Initial Snapshot

This image confirms the successful creation of 100 synthetic sales records in `custom_data.csv`, displaying the initial dataset structure including transaction and timestamp fields.

![Data Generation Output](image.png)

### Comprehensive Data Extraction

This screenshot shows the result of the "Full Extraction," confirming that the entire `custom_data.csv` dataset has been loaded, along with row/column counts and a data sample.

![Full Extraction Output](image-1.png)

### Simulating New Data for Updates

Before the incremental run, this image demonstrates the addition of new records to `custom_data.csv`, mimicking live system updates.

![Simulate New Data](image-3.png)

### Incremental Data Capture

This final image highlights the outcome of the "Incremental Extraction," showcasing the `last_extraction_timestamp` and specifically the new or updated records (e.g., 4 rows) captured since the last check.

![Incremental Extraction Output](image-2.png)

## ✨ Final Thoughts

This project effectively demonstrates both comprehensive and incremental data extraction methodologies, vital for building efficient and scalable data pipelines. The detailed explanations and practical demonstrations within the notebook and this README aim to provide a thorough understanding of these concepts.


