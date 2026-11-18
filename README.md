# Olist E-commerce Sales & Delivery Performance Analysis

An end-to-end data analysis project using **Python, SQL and Power BI** on a real Brazilian e-commerce dataset (about 100k orders across 9 linked tables). The goal is to answer practical business questions about sales, delivery performance, customer behaviour and customer satisfaction.

> **Project status:** In progress. Sections marked *(to be completed)* are filled in as the project is built.

---

## Business problem

An online marketplace wants to understand where its revenue comes from, whether delivery problems are hurting customer satisfaction, and how its customers behave. This project turns raw transactional data into clear answers and recommendations.

## Business questions

1. How are revenue and order volumes trending, and is there seasonality?
2. Which product categories and sellers drive the revenue, and how concentrated is it?
3. Does late delivery (actual vs promised date) hurt customer review scores?
4. What does customer behaviour look like: repeat purchase rate and customer segments (RFM)?
5. Which states have the slowest deliveries and the highest freight cost relative to order value?

## Dataset

- **Source:** *Brazilian E-Commerce Public Dataset by Olist* on Kaggle: https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce
- **Size:** roughly 100k orders (2016 to 2018) spread across 9 related tables: orders, order items, payments, reviews, customers, sellers, products, geolocation and a category-name translation table.
- **Licence:** please check the licence on the Kaggle dataset page before reusing the data.
- The raw data files are **not included in this repository**. See [How to reproduce](#how-to-reproduce) for how to download them.

## Tools and how each is used

| Tool | Role in this project |
|---|---|
| **Python** (pandas, matplotlib, seaborn) | Load the CSV files into a database, check data quality, clean the data, exploratory analysis, correlation checks |
| **SQL** (SQLite) | The analytical layer: multi-table joins, CTEs, window functions (`ROW_NUMBER`, `NTILE`, `LAG`), and final views for the dashboard |
| **Power BI** | Data model, DAX measures and an interactive dashboard that tells the story |
| **VS Code + Git/GitHub** | Development environment and version control |

**In short:** Python gets the data clean and understood, SQL answers the business questions, Power BI communicates the answers.

## Project structure

```
olist-ecommerce-analysis/
├── README.md
├── requirements.txt
├── .gitignore
├── data/
│   ├── raw/                  # original Kaggle CSV files (not committed)
│   └── processed/            # cleaned files used by Power BI
├── database/                 # SQLite database (not committed)
├── notebooks/
│   ├── 01_data_loading.ipynb
│   ├── 02_data_quality_and_cleaning.ipynb
│   └── 03_exploratory_analysis.ipynb
├── sql/
│   ├── 01_revenue_trends.sql
│   ├── 02_category_and_seller_performance.sql
│   ├── 03_delivery_vs_reviews.sql
│   ├── 04_customer_behaviour_rfm.sql
│   ├── 05_state_delivery_and_freight.sql
│   └── 06_dashboard_views.sql
└── dashboard/
    ├── olist_dashboard.pbix
    └── screenshots/
```

## Methodology

1. **Load:** read the raw CSV files and load them into a SQLite database *(to be completed)*
2. **Profile and clean:** check missing values, duplicates, data types and date formats; translate category names; create a clean version of each table *(to be completed)*
3. **Explore:** distributions, trends and relationships in Python *(to be completed)*
4. **Analyse:** answer each business question with a documented SQL query *(to be completed)*
5. **Model and visualise:** build a star-schema model and an interactive Power BI dashboard *(to be completed)*
6. **Report:** summarise findings and recommendations *(to be completed)*

## Key findings

*(To be completed once the analysis is finished.)*

## Recommendations

*(To be completed once the analysis is finished.)*

## Dashboard

*(Screenshots to be added in `dashboard/screenshots/`.)*

## How to reproduce

1. Clone this repository.
2. Create and activate a Python virtual environment, then install the requirements:
   ```
   pip install -r requirements.txt
   ```
3. Download the dataset from the Kaggle link above and place the CSV files in `data/raw/`.
4. Run the notebooks in order (`01` to `03`). Notebook `01` creates the SQLite database in `database/`.
5. Run the SQL files in `sql/` against that database (the queries are numbered to match the business questions).
6. Open `dashboard/olist_dashboard.pbix` in Power BI Desktop.

## Limitations

*(To be completed. For example: the data covers only 2016 to 2018, and review scores reflect only customers who chose to leave a review.)*

## Author

**Kharendwe**
GitHub: [Kharendwenegota](https://github.com/Kharendwenegota)
