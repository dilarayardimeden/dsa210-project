# DSA210 Term Project

# 🎬 Is There an Optimal Movie Runtime for Higher Audience Ratings?

## 📊 DSA 210 — Spring 2026 Term Project

**Author:** Dilara Yardımeden

---

# Project Overview

This project investigates whether movie runtime has a statistically significant effect on audience ratings.

Using the TMDb 5000 Movies Dataset, the analysis explores relationships between runtime and audience ratings through exploratory data analysis (EDA), hypothesis testing, regression models, and machine learning techniques.

The project also examines whether there is an “optimal” runtime range associated with higher audience ratings.

In addition to the main TMDb movie dataset, enrichment datasets were incorporated to strengthen the analysis. Production-related variables such as director information and cast size were extracted from the TMDb Credits dataset, while an external Rotten Tomatoes dataset was used to validate audience rating patterns across a different movie rating platform.

---

# Research Question

**Does movie runtime significantly affect audience ratings, and is there an optimal runtime range for highly rated movies?**

---

# Datasets

## Primary Dataset

* TMDb 5000 Movies Dataset
* Source: Kaggle
* File used:

  * `tmdb_5000_movies.csv`

Dataset Link:
[https://www.kaggle.com/datasets/tmdb/tmdb-movie-metadata](https://www.kaggle.com/datasets/tmdb/tmdb-movie-metadata)

---

## Enrichment Dataset

* TMDb 5000 Credits Dataset
* Source: Kaggle
* File used:

  * `tmdb_5000_credits.csv`

The credits dataset was used as an enrichment source to extract additional production-related variables such as:

* cast size
* director information
* enriched production metadata

These features were incorporated into:

* exploratory data analysis
* hypothesis testing
* regression analysis
* machine learning models

---

## External Validation Dataset

* Rotten Tomatoes Movies Dataset
* Source: Kaggle
* File used:

  * `rotten_tomatoes_movies.csv`

Dataset Link:
[https://www.kaggle.com/datasets/stefanoleone992/rotten-tomatoes-movies-and-critic-reviews-dataset](https://www.kaggle.com/datasets/stefanoleone992/rotten-tomatoes-movies-and-critic-reviews-dataset)

This external dataset was integrated to compare audience rating behavior across different movie rating platforms and to strengthen the enrichment component of the project.

---

# Important Note About Dataset Files

The `tmdb_5000_credits.csv` dataset is relatively large and could not be uploaded directly to this GitHub repository due to file size limitations.

To fully reproduce the analysis, the file should be downloaded manually from the original Kaggle dataset page and placed in the same directory as the notebook before running the project.

Required dataset files:

* `tmdb_5000_movies.csv`
* `tmdb_5000_credits.csv`
* `rotten_tomatoes_movies.csv`

---

# Project Structure

```text
dsa210-project/
│
├── notebooks/
│   └── optimal_movie_runtime_analysis_final.ipynb
│
├── data/
│   ├── tmdb_5000_movies.csv
│   ├── tmdb_5000_credits.csv
│   └── rotten_tomatoes_movies.csv
│
├── figures/
│   ├── fig01_runtime_distribution.png
│   ├── fig02_runtime_vs_rating.png
│   ├── fig03_bar_bucket_ratings.png
│   ├── fig04_boxplot_buckets.png
│   ├── fig05_linear_regression.png
│   ├── fig06_poly_regression.png
│   ├── fig07_cast_size_rating.png
│   └── fig08_actual_vs_predicted.png
│
└── README.md
```

---

# Methods Used

## Exploratory Data Analysis (EDA)

The project begins with data cleaning and visualization techniques to understand:

* runtime distributions
* rating distributions
* runtime vs rating relationships
* enriched production-related variables

Visualizations include:

* histograms
* scatter plots
* boxplots
* bar charts
* regression plots

---

# Hypothesis Testing

Several statistical tests were applied:

## ANOVA Test

Used to determine whether average ratings significantly differ across runtime groups.

## Pearson Correlation Test

Used to measure the strength of the linear relationship between runtime and ratings.

## T-Test (High Cast Size vs Low Cast Size)

Performed using the enriched cast size feature extracted from the credits dataset.

---

# Regression Analysis

## Simple Linear Regression

Examined whether runtime alone predicts audience ratings.

## Multiple Linear Regression

Extended the model using enriched features such as cast size.

## Polynomial Regression

Used to capture non-linear relationships between runtime and ratings.

The polynomial model suggested a non-linear trend where ratings increase up to a point and then stabilize.

---

# Machine Learning Analysis

A machine learning model was built using:

* runtime
* vote count
* cast size

The model was evaluated using:

* RMSE
* R² score

Actual vs predicted rating visualizations were also included to evaluate prediction performance.

---

# External Dataset Validation

The Rotten Tomatoes dataset was incorporated as an external validation source.

A strong positive correlation was observed between TMDb ratings and Rotten Tomatoes audience ratings, suggesting that audience evaluation patterns remain relatively consistent across different movie rating platforms.

This enrichment step helped strengthen the reliability of the overall runtime-rating analysis.

---

# Key Findings

* Runtime has a statistically significant relationship with audience ratings.
* Longer movies generally tend to receive slightly higher ratings.
* Movies in the 120–160 minute range consistently show relatively high ratings across larger numbers of observations.
* Extremely long movies should be interpreted carefully because they are relatively underrepresented in the dataset.
* Runtime alone is not sufficient to fully explain audience ratings.
* Additional production-related factors likely influence movie success.
* Enriched datasets improved the depth and explanatory power of the analysis.

---

# Limitations

This project has several limitations:

* audience ratings are influenced by many external variables not included in the dataset
* genre, budget, marketing, storytelling quality, and audience expectations are not fully modeled
* very long movies are underrepresented in the dataset
* movie ratings are inherently subjective
* the analysis focuses primarily on audience ratings rather than professional critic evaluations

Future studies could incorporate richer external datasets and more advanced machine learning models.

---

# How to Run

## 1. Clone the repository

```bash
git clone https://github.com/dilarayardimeden/dsa210-project.git
```

---

## 2. Install required libraries

```bash
pip install pandas numpy matplotlib seaborn scipy scikit-learn
```

---

## 3. Download required datasets

TMDb Dataset:
[https://www.kaggle.com/datasets/tmdb/tmdb-movie-metadata](https://www.kaggle.com/datasets/tmdb/tmdb-movie-metadata)

Rotten Tomatoes Dataset:
[https://www.kaggle.com/datasets/stefanoleone992/rotten-tomatoes-movies-and-critic-reviews-dataset](https://www.kaggle.com/datasets/stefanoleone992/rotten-tomatoes-movies-and-critic-reviews-dataset)

---

## 4. Place dataset files in the appropriate directory

```text
data/
```

Required files:

* `tmdb_5000_movies.csv`
* `tmdb_5000_credits.csv`
* `rotten_tomatoes_movies.csv`

---

## 5. Open and run the notebook

```text
notebooks/optimal_movie_runtime_analysis_final.ipynb
```

---

# Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* SciPy
* Scikit-learn
* Google Colab

---

# Final Conclusion

The findings suggest that movie runtime does influence audience ratings, but the relationship is not strictly linear and should be interpreted carefully.

While moderately longer movies often receive higher ratings, runtime alone cannot fully explain audience preferences. Enriched production-related features improve the analysis and provide a more comprehensive understanding of factors associated with movie ratings.

The integration of external validation through Rotten Tomatoes ratings further strengthened the reliability of the findings.

---

# Repository

GitHub Repository:

[https://github.com/dilarayardimeden/dsa210-project](https://github.com/dilarayardimeden/dsa210-project)

---

**DSA 210 — Spring 2026**
