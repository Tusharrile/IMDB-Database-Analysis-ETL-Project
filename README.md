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

1. Open the notebook: [ETL project.ipynb]
2. Run the cells sequentially to reproduce the ETL steps and visualizations.
3. After running, the notebook writes a cleaned CSV: [imdb_movies_cleaned.csv](imdb_movies_cleaned.csv).

## Notebook highlights

- Data loading and initial inspection from [imdb_movies.csv](imdb_movies.csv).
- Cleaning steps: handling missing values, standardizing columns, parsing dates, and normalizing numeric fields.
- Business-rule applications as described in [IMDB Movie Business Rules and dashboard_problems statements.txt](IMDB%20Movie%20Business%20Rules%20and%20dashboard_problems%20statements.txt).
- Visualizations for release trends, top genres, rating distributions, and revenue analysis.

## Results

### 1. Top 10 Highest Grossing Movies by Year
<img width="571" height="476" alt="gross_million" src="https://github.com/user-attachments/assets/2d250ad8-1ff7-4061-b5b5-cd9103c39562" />

**Key Insights:**
- The top 10 highest-grossing films maintain uniform revenue (~600M) across all years
- Demonstrates strong and consistent commercial success in the industry
- No declining trend in top-tier movie revenues over the analyzed period

---

### 2. Average Rating by Genre
<img width="580" height="455" alt="unknown" src="https://github.com/user-attachments/assets/0e624ad0-e753-46d0-a460-ac8316e3d945" />

**Key Insights:**
- Sci-Fi genre receives the highest average ratings from audiences
- Horror genre tends to receive lower ratings despite popularity
- Comedy and Drama show below-average ratings (6.48, 6.47)
- Romance and Fantasy show moderate recovery in ratings

---

### 3. Top 5 Directors by Average Rating
<img width="576" height="455" alt="unknown" src="https://github.com/user-attachments/assets/4779d295-faec-4449-95a8-5a89346dd41f" />


**Key Insights:**
- Top directors cluster in a narrow rating range (6.45-6.60)
- Scorsese, Spielberg lead among named directors
- All top directors maintain quality above 6.45 average rating
- Directorial prowess ensures consistent audience satisfaction

---

### 4. Budget vs Gross Revenue Analysis
<img width="576" height="455" alt="Top 5 Directors by Average Rating" src="https://github.com/user-attachments/assets/63057daf-de83-4a12-8cfa-ad1f9ed511c0" />

**Key Insights:**
- **Correlation coefficient: 0.0051** - Virtually no linear relationship between budget and gross
- Budget is NOT a predictor of box office success
- High-budget films don't guarantee high returns
- Success depends on other factors: marketing, genre, timing, director reputation, etc.
- Both low-budget and high-budget films can achieve significant revenues

### 5. Most Profitable Genre
<img width="589" height="455" alt="Most Profitable Genre" src="https://github.com/user-attachments/assets/452d8d4c-e506-454e-bfb7-f72f525e82aa" />

**Key Insights:**
- Fantasy emerges as the most profitable genre overall
- Thriller and Action genres closely follow in total profitability
- Horror generates the lowest total profit among all genres
- Profit margins are relatively competitive across genres
- Genre selection plays a significant role in long-term revenue performance

---

## Database

To load the cleaned dataset into a relational database:

1. Execute the DDL script:
```bash
mysql -u root -p imdb_analysis < imdb_ddl.sql
```

2. Update the database connection in the notebook:
```python
gine = create_engine(
    "mysql+mysqlconnector://root:PASSWORD@localhost:3306/imdb_analysis"
)
```

3. Run the notebook to populate the database
