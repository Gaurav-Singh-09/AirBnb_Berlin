# Airbnb Berlin Data Pipeline & Exploratory Data Analysis (EDA)

An end-to-end data engineering and analytics project built with **Python**, **Pandas**, **SQLAlchemy**, **MySQL**, **Matplotlib**, and **Seaborn**. This pipeline automates the ingestion of large compressed Airbnb datasets into a MySQL database, performs data cleaning, and extracts actionable insights regarding pricing strategies and guest satisfaction across Berlin neighborhoods.

---

## 🚀 Project Architecture & Workflow

1. **Database Ingestion (`load_data_sql`)**: 
   - Iterates through compressed source files (`calendar.csv.gz`, `listings.csv.gz`, `reviews.csv.gz`, and `neighbourhoods.csv`) using memory-efficient chunking (`chunksize = 50,000`).
   - Dynamically creates and populates tables in a local MySQL database via SQLAlchemy.
2. **Data Cleaning & Preprocessing**:
   - Handles missing values (e.g., median imputation for review ratings, string cleaning for comments).
   - Filters out extreme price outliers (`nightly_price < 500`) to ensure reliable statistical distributions.
3. **Exploratory Data Analysis & Visualization**:
   - **Price vs. Room Type:** Analyzes how nightly rates vary across different accommodation types using Seaborn boxplots.
   - **Text & Sentiment Heuristics:** Scans review comments for keywords (`loud|noisy|irritating|disgusting|frustrating|annoying`) to isolate and rank the top noisy neighborhoods and complaint trends over time.

---

## 🛠️ Tech Stack

* **Language:** Python 3.13+
* **Database:** MySQL, MySQL Connector, SQLAlchemy
* **Data Manipulation:** pandas, NumPy
* **Visualization:** Matplotlib, Seaborn

---

## 📁 Project Structure

```text
airbnb_berlin_project/
│
├── notebooks/
│   └── Untitled.ipynb       # Main pipeline, SQL ingestion, and EDA notebook
├── data/                    # Raw dataset files (.csv.gz)
├── requirements.txt         # Project dependencies
└── README.md                # Project documentation