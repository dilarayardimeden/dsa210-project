# Is There an Optimal Movie Runtime for Higher Audience Ratings?

## Project Overview

This project investigates whether movie runtime has a meaningful relationship with audience ratings. The main goal is to understand whether there is an optimal movie duration range that tends to receive higher ratings, and whether production-related features from a second dataset can improve the analysis.

The project uses the **TMDb 5000 Movies Metadata** dataset together with the **TMDb 5000 Credits** dataset from Kaggle. By combining these two datasets, the analysis goes beyond runtime alone and includes additional information such as **director** and **cast size**.

The central question of the project is:

> Does movie runtime affect audience ratings, and is there an optimal duration range that consistently leads to higher scores?

---

## Research Question

Does movie runtime affect audience ratings?  
Is there an optimal runtime range that receives higher audience ratings more consistently?

The project also asks whether production-related features, especially cast size, provide additional explanatory power when analyzing movie ratings.

---

## Hypothesis

**Null Hypothesis (H0):**  
Movie runtime and production-related features have no significant relationship with audience ratings.

**Alternative Hypothesis (H1):**  
Movie runtime has a statistically significant relationship with audience ratings, and production-related features such as cast size may provide additional insight into rating differences.

---

## Dataset

The project uses the **TMDb 5000 Movie Dataset** from Kaggle:

https://www.kaggle.com/datasets/tmdb/tmdb-movie-metadata

Two files are used:

- `tmdb_5000_movies.csv`
- `tmdb_5000_credits.csv`

The movies dataset contains information such as movie title, runtime, vote average, and vote count.  
The credits dataset contains cast and crew information.

After merging and cleaning the data, the final analysis uses **4,139 movies**.

---

## Data Preparation

The two datasets are merged using the movie title as the common column.

From the credits dataset, two additional features are created:

- **Director:** extracted from the crew information
- **Cast Size:** calculated by counting the number of actors listed for each movie

The dataset is then cleaned by:

- Removing missing runtime and rating values
- Keeping movies with runtime between 40 and 300 minutes
- Keeping movies with at least 20 votes
- Selecting relevant columns for analysis

The final selected columns are:

- `title`
- `runtime`
- `vote_average`
- `vote_count`
- `director`
- `cast_size`

---

## Exploratory Data Analysis

The exploratory analysis focuses on the relationship between runtime and audience ratings.

Several visualizations are used:

- Scatter plot of runtime vs. rating
- Correlation analysis
- Runtime bucket comparison
- Bar chart of average rating by runtime group
- Boxplot of rating distribution by runtime group
- Scatter plot of cast size vs. rating

The initial results show that longer movies tend to receive higher ratings on average. However, the relationship is not strong enough to say that runtime alone determines movie quality.

Most movies are concentrated between approximately **80 and 140 minutes**, while higher-rated movies are more commonly observed in moderately longer runtime ranges.

---

## Runtime Buckets

Runtime is grouped into the following categories:

- 40–80 minutes
- 81–100 minutes
- 101–120 minutes
- 121–140 minutes
- 141–160 minutes
- 160+ minutes

The average ratings generally increase as runtime increases. Movies shorter than 100 minutes tend to have lower average ratings, while movies in the **120–160 minute range** show more consistently high ratings.

Although movies longer than 160 minutes have high average ratings, this group contains fewer observations, so it should be interpreted carefully.

---

## Hypothesis Testing

Three statistical tests are applied:

### 1. ANOVA Test

ANOVA is used to test whether average ratings differ significantly across runtime groups.

The result shows a very small p-value, meaning that rating differences across runtime groups are statistically significant.

This supports the idea that runtime is related to audience ratings.

### 2. Pearson Correlation Test

The correlation between runtime and vote average is approximately **0.40**.

This indicates a moderate positive relationship. In other words, longer movies tend to receive higher ratings on average, but the relationship is not strong enough to fully explain rating differences.

### 3. T-Test for Cast Size

A t-test is used to compare ratings between movies with high cast size and low cast size.

The result is statistically significant, suggesting that movies with larger and smaller casts have different average ratings. However, cast size should not be interpreted as a direct cause of higher ratings. It is only one production-related feature, and movie ratings are influenced by many other factors.

---

## Regression Analysis

### Simple Linear Regression

A simple linear regression model is built using runtime as the only predictor of audience rating.

The model is:

```text
vote_average = 4.4033 + 0.0171 × runtime
```

The slope is positive, meaning that each additional minute of runtime is associated with a small increase in average rating.

However, the model has an R² value of approximately **0.16**, meaning runtime explains only about 16% of the variation in ratings. This shows that runtime matters, but it is not enough on its own to predict audience ratings accurately.

### Multiple Linear Regression

A second regression model includes both runtime and cast size.

Features used:

- `runtime`
- `cast_size`

The R² value increases slightly to approximately **0.168**. This means cast size adds a small amount of explanatory power, but the improvement is limited.

This result supports the idea that the credits dataset enriches the project, but movie ratings are still affected by many factors not included in this model.

### Polynomial Regression

A polynomial regression model is also used to capture a possible non-linear relationship between runtime and ratings.

The model suggests a peak around **227 minutes**, but this result should be interpreted carefully because very long movies are rare in the dataset and may be affected by outliers.

A more reliable interpretation is that movies in the **120–160 minute range** tend to receive consistently higher ratings across a larger number of observations.

---

## Machine Learning Analysis

A machine learning model is used to predict movie ratings using:

- `runtime`
- `vote_count`
- `cast_size`

The dataset is split into training and testing sets using an 80/20 split.

The model achieves:

- **RMSE:** approximately 0.76
- **R²:** approximately 0.24

This means the model explains about 24% of the variation in movie ratings.

The result shows that runtime, vote count, and cast size provide some useful information, but they are not enough to fully predict audience ratings. Factors such as genre, budget, storytelling quality, marketing, and audience preferences likely play a larger role.

---

## Key Findings

- Runtime has a statistically significant relationship with audience ratings.
- The correlation between runtime and rating is moderately positive.
- Movies in the **120–160 minute range** tend to receive consistently higher ratings.
- Very long movies may have high ratings, but there are fewer of them, so results for that group should be interpreted carefully.
- Cast size adds some extra information, but it does not strongly explain rating differences by itself.
- Regression and machine learning models show that runtime matters, but it is not the only factor behind audience ratings.

---

## Conclusion

The analysis shows that movie runtime is statistically related to audience ratings. Longer movies tend to receive higher ratings on average, and the most reliable runtime range appears to be around **120–160 minutes**.

However, runtime alone does not fully explain why some movies receive higher ratings than others. The regression results show that runtime explains only a limited part of rating variation. Even after adding vote count and cast size, the model still leaves a large amount of variation unexplained.

Therefore, the null hypothesis is rejected. Movie runtime has a statistically significant relationship with audience ratings, but it should be interpreted as one factor among many rather than the main reason behind a movie’s success.

---

## Limitations

This project has several limitations:

- The dataset does not fully capture movie quality.
- Ratings may be affected by popularity, fan bases, marketing, or cultural impact.
- Very long movies are less common, which can make the polynomial model sensitive to outliers.
- Important features such as genre, budget, revenue, language, and release year are not deeply analyzed in the current version.
- Cast size does not necessarily represent production quality.

---

## Future Work

Future versions of this project could improve the analysis by:

- Adding genre-based comparisons
- Including budget and revenue
- Analyzing release year effects
- Comparing director-level patterns
- Testing more advanced machine learning models
- Using cross-validation for more reliable model evaluation
- Studying whether runtime affects ratings differently across genres

---

## How to Run

1. Download the dataset from Kaggle:
   https://www.kaggle.com/datasets/tmdb/tmdb-movie-metadata

2. Place the following files in the same folder as the notebook:

   - `tmdb_5000_movies.csv`
   - `tmdb_5000_credits.csv`

3. Open the notebook:

   - `optimal_movie_runtime_analysis.ipynb`

4. Run the cells in order.

---

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- SciPy
- scikit-learn
- Google Colab

---

## Project Structure

```text
.
├── optimal_movie_runtime_analysis.ipynb
├── tmdb_5000_movies.csv
├── tmdb_5000_credits.csv
├── README.md
└── figures/
```

The notebook also saves several figures, including:

- `fig02_scatter_runtime_rating.png`
- `fig03_bar_bucket_ratings.png`
- `fig04_boxplot_buckets.png`
- `fig06_poly_regression.png`
- `fig07_cast_size_rating.png`
- `fig08_actual_vs_predicted.png`

---

## Author

**Dilara Yardımeden**  
DSA 210 — Spring 2026 Term Project
