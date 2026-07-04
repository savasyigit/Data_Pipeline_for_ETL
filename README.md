# ETL Pipeline with Python, Pandas, and PostgreSQL

## Overview

This project demonstrates how to build a complete **ETL (Extract, Transform, Load)** pipeline using **Python**, **Pandas**, **SQLAlchemy**, and **PostgreSQL**.

The pipeline reads Google Play Store application data from CSV files, performs several data cleaning and transformation operations, and loads the processed dataset into a PostgreSQL database for further analysis.

This project is designed as a beginner-friendly example of a real-world ETL workflow and demonstrates the core stages of a modern data engineering pipeline.

---

## Project Structure

```
.
├── apps_data.csv
├── review_data.csv
├── top_apps.csv
├── etl_pipeline.ipynb
├── README.md

```

---

## Dataset

The project uses the **Google Play Store Apps** dataset consisting of two CSV files:

* **apps_data.csv**

  * Application information
  * Category
  * Rating
  * Number of reviews
  * Number of installs

* **review_data.csv**

  * User reviews
  * Sentiment polarity scores

---

## Technologies Used

* Python
* Pandas
* PostgreSQL
* SQLAlchemy
* psycopg2
* Jupyter Notebook

---

## ETL Workflow

### 1. Extract

The pipeline begins by reading data from CSV files using Pandas.

During this stage:

* Data is loaded into DataFrames.
* Basic exploratory analysis is performed.
* Dataset dimensions and data types are inspected.

---

### 2. Transform

The extracted data is cleaned and transformed before loading.

Transformation steps include:

* Removing duplicate records
* Filtering only **FOOD_AND_DRINK** applications
* Joining applications with their reviews
* Calculating the average sentiment polarity
* Selecting only the required columns
* Filtering applications based on:

  * Rating greater than **4.0**
  * More than **1000** reviews
* Sorting applications by rating and review count
* Exporting the transformed dataset as **top_apps.csv**

---

### 3. Load

The transformed dataset is loaded into a PostgreSQL database using SQLAlchemy.

The loading process includes:

* Connecting to PostgreSQL
* Creating or replacing the destination table
* Writing the DataFrame into the database
* Reading the table back for validation
* Comparing the original and loaded datasets

---

## Database

The project stores the processed data in a PostgreSQL table.

**Example table**

```
top_apps
```

The table is automatically created (or replaced) during execution.

---

## Project Features

* Modular ETL design
* Reusable Python functions
* Clean and readable code
* Data validation after loading
* PostgreSQL integration
* Well-documented workflow
* Beginner-friendly implementation

---

## Learning Outcomes

This project demonstrates how to:

* Build a complete ETL pipeline
* Read and process CSV files with Pandas
* Perform data cleaning and transformation
* Aggregate and merge datasets
* Connect Python to PostgreSQL
* Load data into a relational database
* Validate data after loading
* Organize an ETL project using reusable functions

---

## How to Run

1. Clone the repository.

```bash
git clone <repository-url>
```

2. Install the required packages.

```bash
pip install -r requirements.txt
```

3. Update the PostgreSQL connection settings.

```python
host="localhost"
port=5432
database="your_database"
user="postgres"
password="your_password"
```

4. Run the Jupyter Notebook.

5. The transformed data will be loaded into PostgreSQL and validated automatically.

---

## Future Improvements

Possible enhancements include:

* Logging support
* Configuration file for database credentials
* Exception handling improvements
* Automated scheduling with Apache Airflow
* Docker support
* Unit testing
* Cloud database integration

---

## License

This project is intended for educational purposes and portfolio demonstration.
