# 🏏 IPL Match Analytics & Win Probability Predictor

A machine learning pipeline that predicts IPL match outcomes **ball-by-ball** using a Random Forest classifier, achieving **89.81% accuracy** on 260,920+ delivery records.

![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python)
![scikit-learn](https://img.shields.io/badge/Scikit--learn-ML-orange?logo=scikit-learn)
![Pandas](https://img.shields.io/badge/Pandas-Data-green?logo=pandas)
![NumPy](https://img.shields.io/badge/NumPy-Compute-blue?logo=numpy)

---

## 📌 Overview

This project analyzes **1,095 IPL matches** and **260,920 ball-by-ball deliveries** to build a real-time win probability prediction model. It includes intelligent data cleaning, advanced feature engineering, and a TV-style analytics dashboard.

## ✨ Key Features

- **Intelligent Data Cleaning** — Standardized team names across franchise changes (e.g., Delhi Daredevils → Delhi Capitals), imputed missing cities from venue names, filtered for 10 active franchises
- **13 Engineered Features** — Including rolling 30-ball momentum windows, current/required run rates, powerplay & death-over flags, toss advantage, and home advantage
- **ML Pipeline** — Scikit-learn Pipeline with OneHotEncoder for categorical features + Random Forest Classifier (100 estimators, max_depth=12)
- **89.81% Accuracy** — Ball-by-ball match outcome prediction
- **5-Panel TV-Style Dashboard** — Win probability chart, momentum heatmap, run rate comparison, worm graph, and batting/bowling MVP with Win Probability Added (WPA)

## 🛠️ Tech Stack

| Category | Tools |
|---|---|
| Language | Python 3 |
| Data Processing | Pandas, NumPy |
| Visualization | Matplotlib, Seaborn |
| Machine Learning | Scikit-learn (RandomForestClassifier, Pipeline, ColumnTransformer, OneHotEncoder) |
| Environment | Google Colab / Jupyter Notebook |

## 📊 Feature Engineering

The model uses **13 numerical + 3 categorical features**:

| Feature | Description |
|---|---|
| `runs_left` | Runs remaining for chasing team |
| `balls_left` | Balls remaining in the innings |
| `wickets_left` | Wickets in hand |
| `target_runs` | Total target set by batting-first team |
| `crr` | Current Run Rate |
| `rrr` | Required Run Rate |
| `runs_last_30` | Runs scored in last 30 balls (momentum) |
| `wickets_last_30` | Wickets lost in last 30 balls |
| `is_powerplay` | Whether current over is in powerplay (1-6) |
| `is_death_over` | Whether current over is in death overs (16-20) |
| `chasing_team_won_toss` | Toss advantage flag |
| `is_home_advantage` | Whether chasing team is playing at home |
| `batting_team` | Current batting team (categorical) |
| `bowling_team` | Current bowling team (categorical) |
| `city` | Match venue city (categorical) |

## 🚀 How to Run

1. **Clone the repository**
   ```bash
   git clone https://github.com/Vedant241/IPL-Match-Analytics.git
   cd IPL-Match-Analytics
   ```

2. **Install dependencies**
   ```bash
   pip install pandas numpy matplotlib seaborn scikit-learn
   ```

3. **Get the data**
   - Download `matches.csv` and `deliveries.csv` from [Kaggle IPL Dataset](https://www.kaggle.com/datasets/patrickb1912/ipl-complete-dataset-20082020)
   - Place them in the project directory
   - Update the file paths in the notebook

4. **Run the notebook**
   ```bash
   jupyter notebook IPL-Match-Analytics.ipynb
   ```

## 📈 Results

- **Model:** Random Forest Classifier (100 trees, max_depth=12)
- **Accuracy:** 89.81%
- **Dashboard Panels:**
  - 🏆 Win Probability — Live win % for both teams across overs
  - 🔥 Momentum Heatmap — Rolling 30-ball scoring intensity
  - 📊 Run Rate Comparison — CRR vs RRR progression
  - 🐛 Worm Graph — Cumulative run chase visualization
  - ⭐ Player Impact — Batting & Bowling MVP ranked by WPA

## 📁 Project Structure

```
IPL-Match-Analytics/
├── IPL-Match-Analytics.ipynb   # Main notebook (EDA + ML + Dashboard)
├── matches.csv                 # Match-level data (1,095 records)
├── deliveries.csv              # Ball-by-ball data (260,920 records)
└── README.md
```

## 📜 License

This project is open source and available under the [MIT License](LICENSE).
