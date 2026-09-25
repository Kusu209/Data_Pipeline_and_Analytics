# Data Pipeline and Analytics Project

End-to-end data workflow spanning two modules: a web-scraping and SQL data pipeline, and an exploratory data analysis / machine learning study on the Titanic dataset. The project demonstrates the full lifecycle of a data project — collection, cleaning, storage, analysis, modeling, and evaluation.

## Table of Contents

- [Project Structure](#project-structure)
- [Module 1: Data Pipeline](#module-1--data-pipeline)
- [Module 2: Titanic Analytics and Machine Learning](#module-2--titanic-analytics-and-machine-learning)
- [Technologies Used](#technologies-used)
- [Getting Started](#getting-started)
- [Author](#author)

## Project Structure

```
.
├── Module_1_data_pipeline.ipynb   # Web scraping, cleaning, SQLite pipeline
├── Module_2_analytics.ipynb       # Titanic EDA and machine learning
└── README.md
```

## Module 1 — Data Pipeline

Builds an end-to-end data pipeline using book data collected from [Books to Scrape](https://books.toscrape.com/), from raw HTML through to a queryable relational database.

**Key tasks**
- Web scraping with Requests and BeautifulSoup across the first five catalogue pages (100 book records)
- Data cleaning and transformation with Pandas (price parsing, star-rating encoding, stock status, deduplication)
- Currency conversion of book prices from GBP to INR at a fixed project rate (1 GBP = 105.50 INR)
- Design and creation of a normalized SQLite database (`categories` and `books` tables, linked by `category_id`)
- SQL querying using `WHERE`, `ORDER BY`, `LIMIT`, `GROUP BY`, `JOIN`, and aggregate functions (`COUNT`, `AVG`, `ROUND`)
- Cross-validation of SQL `JOIN` output against an equivalent `pd.merge()` result in Pandas

## Module 2 — Titanic Analytics and Machine Learning

Performs exploratory data analysis and predictive modeling on the Titanic dataset, covering both a classification task (survival) and a regression task (fare).

**Key tasks**
- Data inspection and missing-value analysis
- Univariate, bivariate, and multivariate exploratory visualizations
- Correlation analysis
- Feature preprocessing and standardization via a `ColumnTransformer` pipeline
- Classification models: Logistic Regression, Decision Tree, Random Forest
- Model evaluation using Accuracy, Precision, Recall, F1-score, and ROC-AUC
- Class imbalance handling via class weighting and SMOTE
- Hyperparameter tuning with `GridSearchCV`
- Linear Regression for fare prediction, evaluated with MAE, RMSE, R², and Adjusted R²
- Model persistence and reloading with Joblib

## Technologies Used

| Category | Tools |
|---|---|
| Language | Python |
| Data handling | Pandas, NumPy |
| Visualization | Matplotlib, Seaborn |
| Machine learning | Scikit-learn, imbalanced-learn (SMOTE) |
| Web scraping | Requests, BeautifulSoup |
| Database | SQLite, SQL |
| Model persistence | Joblib |

## Getting Started

1. Clone or download this repository.
2. Install the required libraries:
   ```
   pip install pandas numpy matplotlib seaborn scikit-learn imbalanced-learn requests beautifulsoup4 joblib
   ```
3. Run each notebook from top to bottom:
   - `Module_1_data_pipeline.ipynb` scrapes the source site, cleans the data, and builds the SQLite database.
   - `Module_2_analytics.ipynb` loads the Titanic dataset, runs the analysis, trains the models, and saves the best-performing pipeline.

## Author

**Kusuma G R**
