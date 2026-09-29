# Spotify Track Popularity Analysis

Exploratory data analysis investigating what drives track popularity on Spotify, using a combined dataset of 17,000+ tracks spanning 2009–2025.

## Overview

This project examines whether explicit content, song duration, and artist follower count are associated with a track's popularity score on Spotify. It was completed as a final project for DSC 101: Introduction to Data Science at the University of Tampa.

## Research Questions

1. Do explicit songs have higher average track popularity than non-explicit songs?
2. Does song duration influence popularity?
3. Do artists with more followers tend to have higher track popularity?

## Dataset

**Source:** [Spotify Global Music Dataset (2009–2025)](https://www.kaggle.com/datasets/wardabilal/spotify-global-music-dataset-20092025) by Warda Bilal, via Kaggle (collected from the Spotify Web API).

Two CSV files were merged into a single combined dataset (17,351 rows × 17 columns) after cleaning:
- `spotify_data clean.csv` — modern tracks (2025)
- `track_data_final.csv` — classic tracks (2009–2023)

## Methods

- **Data cleaning:** Handled missing values (dropped rows with missing critical fields; imputed missing genre data as "Unknown" rather than dropping to preserve sample size), standardized duration units (ms → minutes) across datasets, and extracted release year from inconsistent date formats.
- **Feature engineering:** Created `release_decade`, `duration_category` (Short/Medium/Long), and `popularity_level` (Low/Medium/High) bins to simplify group comparisons.
- **Analysis:** Descriptive statistics, histograms, boxplots, scatter plots, a pair plot, and Pearson correlation.

## Key Findings

| Question | Result |
|---|---|
| Explicit vs. non-explicit popularity | Explicit tracks average **~7–8 points higher** popularity |
| Duration and popularity | Short tracks average **~42**; medium/long tracks average **~54–55** — length matters mainly at the low end |
| Followers and popularity | Weak positive correlation (**r ≈ 0.23**) — follower count alone doesn't strongly predict popularity |

Full write-up and visualizations are in the notebook.

## Tech Stack

- Python (pandas, NumPy, Matplotlib, Seaborn)
- Jupyter Notebook

## Repository Structure

```
spotify-track-popularity-analysis/
├── README.md
├── spotify_data_analysis.jpynb.ipynb
├── spotify_data_analysis.pdf
├── spotify_data clean.csv
└── track_data_final.csv
```

## Running This Project

```bash
git clone https://github.com/gabep06/spotify-track-popularity-analysis.git
cd spotify-track-popularity-analysis
pip install pandas numpy matplotlib seaborn jupyter
jupyter notebook spotify_data_analysis.jpynb.ipynb
```

## Future Work

Build a predictive model (e.g., regression or gradient boosting) that estimates track popularity from multiple variables simultaneously, rather than examining each factor in isolation.

## Author

Gabriel Pereira — B.S. Data Science, University of Tampa
[LinkedIn](http://www.linkedin.com/in/gabriel-pereira-05b593359) · [GitHub](https://github.com/gabep06)
