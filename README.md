# 🎬 Letterboxd Movie Rating Prediction

End-to-end data analysis and machine learning project predicting movie ratings using the [Letterboxd dataset](https://www.kaggle.com/datasets/gsimonx37/letterboxd) — from raw relational data to a trained regression model and an interactive Power BI dashboard.

## 📊 Project Overview

This project analyzes **90,999 films** across 9 relational tables (movies, actors, crew, genres, studios, countries, languages, themes, releases) to understand what drives audience ratings and build a model that predicts a film's average rating from its metadata.

**Pipeline:**
1. **Data Exploration** — inspected 9 raw CSV tables from Kaggle
2. **Cleaning & Merging** — aggregated auxiliary tables (actors, crew, genres, etc.) to one row per film, engineered 6 boolean release-type features, left-joined everything into a single clean dataset (941,597 → 90,999 rated films)
3. **Exploratory Data Analysis (SQL/DuckDB)** — answered 7 analytical questions about genre, duration, director, and distribution effects on rating
4. **Machine Learning** — compared Linear Regression, Decision Tree, and Random Forest regressors
5. **Power BI Dashboard** — multi-page interactive dashboard with KPIs, genre/country/duration breakdowns, and model comparison

## 🔍 Key Findings

| Finding | Detail |
|---|---|
| Highest-rated genre | Documentary (3.51 avg) |
| Lowest-rated genre | Horror (2.90 avg) |
| Duration effect | U-shaped relationship — very short and very long films rate higher than mid-length films |
| Distribution effect | Premiere / Theatrical Limited releases correlate with higher ratings; Digital/Physical correlate with lower ratings |
| Overall pattern | Niche, selective production tends to score higher than mass-market production |

## 🤖 Model Performance

Three regression models were trained and compared to predict a film's rating:

| Model | MAE | RMSE | R² |
|---|---|---|---|
| Linear Regression | 0.2650 | 0.3554 | 0.278 |
| Decision Tree | 0.2411 | 0.3288 | 0.382 |
| **Random Forest** | **0.2316** | **0.3157** | **0.430** |

**Random Forest** was selected as the final model — it captured the non-linear relationships in the data (like the U-shaped duration effect) that the linear model missed.

## 🛠️ Tech Stack

- **Python** (pandas, scikit-learn) — data cleaning, feature engineering, modeling
- **DuckDB / SQL** — exploratory data analysis
- **Google Colab** — development environment
- **Power BI** — dashboard and visualization
- **Kaggle API** — dataset access

## 📁 Repository Contents

- `Letterboxd_Rating_Prediction.ipynb` — full notebook: data cleaning, EDA, modeling
- `movies_clean.csv` — final cleaned dataset (90,999 rows × 23 columns) used for analysis and modeling
- `LetterBoxd_PowerBI_Final.pbix` — Power BI dashboard file
- `Letterboxd_Sunum.pptx` — final presentation summarizing the project

## 📦 Dataset

- **Source:** [Kaggle — gsimonx37/letterboxd](https://www.kaggle.com/datasets/gsimonx37/letterboxd)
- **License:** GPL-3.0
- **Structure:** 9 relational CSV tables joined on film ID

## 🚀 How to Run

1. Get a Kaggle API token from [kaggle.com/settings](https://www.kaggle.com/settings) → API section
2. Open `Letterboxd_Rating_Prediction.ipynb` in Google Colab
3. When prompted, enter your Kaggle API token (it is **not** stored in the notebook)
4. Run all cells — the notebook downloads the dataset, cleans it, runs EDA, and trains the models

## 📄 License

This project is licensed under the MIT License — see the [LICENSE](LICENSE) file for details. The underlying dataset is licensed separately under GPL-3.0 by its original author.

---

## 🇹🇷 Türkçe Özet

Bu proje, Letterboxd film veri seti (90.999 film) üzerinde uçtan uca bir veri analizi ve makine öğrenmesi çalışmasıdır. Veri temizleme, SQL/DuckDB ile keşifsel analiz, üç farklı regresyon modelinin (Linear Regression, Decision Tree, Random Forest) karşılaştırılması ve çok sayfalı bir Power BI dashboard'u içerir.

**Öne çıkan bulgular:** Documentary türü en yüksek ortalama puana sahip (3.51), Horror en düşük (2.90); film süresi ile puan arasında U-şekilli bir ilişki var; niş/seçici dağıtımla çıkan filmler (Premiere, Theatrical Limited) daha yüksek puan alıyor. En iyi model **Random Forest** oldu (R²=0.43, MAE=0.23).

Detaylı Türkçe anlatım için proje sunumuna (`Letterboxd_Sunum.pptx`) göz atabilirsiniz.
