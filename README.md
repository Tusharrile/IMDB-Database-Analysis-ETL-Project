# IMDB Movie Dataset Analysis (Project 1)

## Overview

This repository contains an exploratory data analysis and ETL notebook for the IMDB movie dataset. The primary work is performed in the Jupyter notebook which cleans the data, applies business rules, and produces visualizations useful for movie business analysis and dashboarding.

## Repository Contents

- [IMDB Movie Business Rules and dashboard_problems statements.txt](IMDB%20Movie%20Business%20Rules%20and%20dashboard_problems%20statements.txt): Business rules and problem statements for the dashboard.
- [imdb_ddl.sql](imdb_ddl.sql): DDL for loading the cleaned dataset into a relational database.
- [imdb_movies.csv](imdb_movies.csv): Original raw dataset (CSV).
- [imdb_movies_cleaned.csv](imdb_movies_cleaned.csv): Cleaned and preprocessed dataset exported from the notebook.
- [imdbmovies_etl.ipynb](imdbmovies_etl.ipynb): Main Jupyter notebook performing ETL and analysis.

## Requirements

- Python 3.8+
- Jupyter or JupyterLab
- Common Python packages: `pandas`, `matplotlib`, `sql alchemy` (install via pip)

## How to run

1. Open the notebook: [imdbmovies_etl.ipynb](ETL project.ipynb)
2. Run the cells sequentially to reproduce the ETL steps and visualizations.
3. After running, the notebook writes a cleaned CSV: [imdb_movies_cleaned.csv](imdb_movies_cleaned.csv).

## Notebook highlights

- Data loading and initial inspection from [imdb_movies.csv](imdb_movies.csv).
- Cleaning steps: handling missing values, standardizing columns, parsing dates, and normalizing numeric fields.
- Business-rule applications as described in [IMDB Movie Business Rules and dashboard_problems statements.txt](IMDB%20Movie%20Business%20Rules%20and%20dashboard_problems%20statements.txt).
- Visualizations for release trends, top genres, rating distributions, and revenue analysis.

## Database

To load the cleaned dataset into a relational database:

1. Execute the DDL script:
```bash
mysql -u root -p imdb_analysis < imdb_ddl.sql
```

2. Update the database connection in the notebook:
```python
engine = create_engine(
    "mysql+mysqlconnector://root:PASSWORD@localhost:3306/imdb_analysis"
)
```

3. Run the notebook to populate the database
