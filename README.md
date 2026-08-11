# NBA Analytics & Distributed Data Pipeline

Distributed data analysis project using **PySpark** to process basketball play-by-play data and study changes in NBA shot selection and efficiency from **2016–2024**, with a 2024 NBA/WNBA comparison.

## Project Overview

The project uses Spark DataFrames to clean, transform, join, cache, and aggregate large play-by-play datasets. The analysis focuses on how shot selection has shifted toward the three-point line, how shooting efficiency has changed, and how NBA and WNBA shot profiles differ.

## Data

- NBA play-by-play data spanning **2016–2024**
- WNBA 2024 play-by-play data for cross-league comparison
- Hundreds of thousands of play-by-play records processed with PySpark

## Distributed Data Pipeline

The notebook demonstrates several Spark-oriented data engineering techniques:

1. Load yearly CSV files into Spark DataFrames.
2. Add league/year metadata and combine datasets.
3. Filter field-goal and free-throw events.
4. Create derived variables such as made-shot indicators and shot distance.
5. Repartition data by year for aggregation.
6. Cache reused intermediate DataFrames.
7. Use broadcast joins for smaller lookup/summary tables.
8. Aggregate attempts, makes, efficiency, fouls, shot type, and scoring composition.
9. Convert compact aggregate results for visualization with Python plotting libraries.

## Selected Results

### 2024 NBA vs. WNBA

| Metric | NBA | WNBA |
| --- | ---: | ---: |
| 2-point FG% | **54.51%** | 48.82% |
| 3-point FG% | **36.02%** | 33.82% |
| Avg. 3-point attempts/game | **75.17** | 45.68 |
| 3-point share of FG attempts | **42.12%** | 33.46% |
| Personal fouls/game | 30.29 | 28.79 |
| Shooting fouls/game | 7.87 | 6.49 |

### NBA Trend: 2016 → 2024

- Three-point share increased from **31.61% to 42.12%** of field-goal attempts.
- Overall field-goal percentage increased from **45.72% to 46.72%**.
- Two-point percentage increased from **50.33% to 54.51%**.
- Three-point accuracy remained comparatively stable around the mid-30% range while attempt volume increased substantially.
- Average shot distance increased over the period, consistent with the league-wide shift toward perimeter shooting.

## Key Findings

The strongest trend is not a dramatic increase in three-point accuracy, but a major increase in **three-point volume**. NBA teams took a much larger share of their shots from three in 2024 than in 2016 while maintaining similar three-point efficiency. At the same time, two-point efficiency improved.

The 2024 cross-league comparison also shows the NBA taking a larger share of attempts from three and recording higher field-goal percentages on both two- and three-point shots in the analyzed data.

## Tech Stack

`Python` · `PySpark` · `Spark DataFrames` · `pandas` · `Matplotlib` · `Seaborn` · `Jupyter/Google Colab`

## Repository Contents

- `NBA_Notebook.ipynb` — complete Spark pipeline, analysis, and visualizations
- `README.md` — project summary and selected findings

## Limitations

This is a descriptive analytics project rather than a predictive model. The WNBA comparison uses only the 2024 season, while the NBA trend analysis covers nine seasons. Results are primarily league-level aggregates and do not control for team, player, lineup, or game-context effects.
