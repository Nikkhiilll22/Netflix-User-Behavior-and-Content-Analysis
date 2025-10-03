# Netflix User Behavior & Content Analysis

[![Jupyter Notebook](https://img.shields.io/badge/notebook-Jupyter-orange)]()
[![Python](https://img.shields.io/badge/python-3.x-blue)]()
[![License: MIT](https://img.shields.io/badge/license-MIT-green)]()

> Data analysis project exploring Netflix content metadata and user viewing behavior — uncovering genre trends, release patterns, regional preferences, and time-based viewing habits.

---

## Table of Contents

- [Project Overview](#project-overview)  
- [What I Did](#what-i-did)  
- [Dataset(s)](#datasets)  
- [Key Questions](#key-questions)  
- [Methodology](#methodology)  
- [Highlights & Insights](#highlights--insights)  
- [How to run (reproduce)](#how-to-run-reproduce)  
- [Project structure](#project-structure)  
- [Dependencies](#dependencies)  

## Project Overview

This repository contains an exploratory data analysis (EDA) notebook investigating Netflix content metadata and user-viewing patterns. The goal is to transform raw catalog & viewing data into actionable insights about what users watch, where they watch, and when they watch it — useful for content strategy, recommendation tuning, and product decisions.

---

## What I Did

- Cleaned and preprocessed Netflix metadata and view logs.
- Performed feature engineering (date parts, aggregated watch counts, genre parsing).
- Visualized trends (genre popularity, additions timeline, country-wise preferences, seasonality).
- Generated clear, visual insights using Matplotlib and Seaborn inside a reproducible Jupyter Notebook (`Nexflix Project.ipynb`).

---

## Datasets

> **Note:** Replace these with exact dataset names or links if you host them here or on Kaggle.

- `netflix_titles.csv` — Catalog metadata (title, type, director, cast, country, date_added, release_year, rating, duration, listed_in/genres).
- `user_viewing_logs.csv` — (Optional) Aggregated viewing logs or play counts with timestamps and country tags.

If your repo currently has only the notebook, make sure to add `.csv` files under `data/` or adjust the notebook to fetch dataset paths.

---

## Key Questions

1. Which content types and genres are the most watched?  
2. How does content addition and release-year distribution change over time?  
3. Which titles and genres perform best in particular countries?  
4. Are there clear seasonal or weekday/weekend effects on viewing?

---

## Methodology

1. **Load** CSV/JSON into Pandas DataFrames.  
2. **Clean**: remove duplicates, parse dates (`date_added`, show release year), handle missing countries/genres.  
3. **Feature engineering**: derive `year`, `month`, `weekday`, `age_on_platform` (difference between `date_added` and `release_year`), and explode multi-genre listings.  
4. **Aggregate** metrics: total views / watch time by title, by genre, by country, and by time window.  
5. **Visualize** using histograms, barplots, heatmaps, lineplots, and time series.  
6. **Summarize**: produce succinct business-focused takeaways.

---

## Highlights & Insights (example)

- **Top genres**: Drama, Documentary, and Comedy dominate watch counts in most regions.  
- **Catalog growth**: Net additions spike in Q3–Q4 across years — likely due to strategic release windows.  
- **Regional tastes**: Crime/Thriller genres perform strongly in Country A and Country B; family/animation show better retention in Country C.  
- **Temporal patterns**: Viewing spikes on weekends and during major holiday months; newly added titles get a short initial spike, while classic titles show long-tail viewing.

---

## How to run / reproduce

```bash
# clone
git clone https://github.com/Nikkhiilll22/Netflix-User-Behavior-and-Content-Analysis.git
cd Netflix-User-Behavior-and-Content-Analysis

# create venv (optional but recommended)
python3 -m venv venv
# mac/linux
source venv/bin/activate
# windows (powershell)
# .\venv\Scripts\Activate.ps1

# install requirements
pip install -r requirements.txt

# open the notebook
jupyter notebook "Nexflix Project.ipynb"

# preprocess script (if present)
python scripts/preprocess.py --input data/netflix_titles.csv --output data/processed_titles.csv

# run analysis script
python scripts/run_analysis.py


