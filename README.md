# DSA210 Term Project

# 🎬 Is There an Optimal Movie Runtime for Higher Audience Ratings?

## 📊 DSA 210 — Spring 2026 Term Project  
**Author:** Dilara Yardımeden  

---

## 🔍 Research Question  
Does movie runtime affect audience ratings?  
Is there an optimal duration range that consistently leads to higher ratings?

---

## 🧠 Hypothesis  

- **H0:** Movie runtime has no significant effect on audience ratings.  
- **H1:** Movie runtime has a statistically significant effect on audience ratings, and an optimal runtime range exists.  

---

## 📁 Dataset  

This project uses the **TMDB 5000 Movies Dataset** from Kaggle:  
https://www.kaggle.com/datasets/tmdb/tmdb-movie-metadata  

Files used:
- `tmdb_5000_movies.csv`  
- `tmdb_5000_credits.csv`  

---

## ⚙️ How to Run  

1. Download the dataset from Kaggle  
2. Place both CSV files in the same folder as the notebook  
3. Open the notebook:  
   `optimal_movie_runtime_analysis.ipynb`  
4. Run all cells  

---

## 🧹 Data Cleaning  

- Selected relevant variables (runtime, vote_average, vote_count)  
- Removed missing values  
- Filtered unrealistic runtimes (40–300 minutes)  
- Removed movies with very low vote counts  

---

## 📈 Exploratory Data Analysis  

- Scatter plot used to visualize relationship between runtime and rating  
- Correlation analysis performed  
- Movies grouped into runtime buckets  
- Bar charts and boxplots used to compare rating distributions  

---

## 🧪 Hypothesis Testing  

A one-way **ANOVA test** was used to determine whether ratings differ significantly across runtime groups.

---

## 📉 Regression Analysis  

- **Linear regression** used to examine overall trend  
- **Polynomial regression** used to capture non-linear patterns  
- Optimal runtime estimated based on model predictions  

---

## 📊 Key Findings  

- Moderate positive correlation between runtime and ratings (**r ≈ 0.37**)  
- ANOVA results show statistically significant differences between runtime groups (**p < 0.05**)  
- Longer movies tend to have higher average ratings  
- The most consistently high-rated movies fall in the **120–160 minute range**  

---

## ✅ Conclusion  

This analysis shows that movie runtime has a statistically significant effect on audience ratings.  

The null hypothesis (H0) is rejected.  

Results indicate that longer movies generally receive higher ratings, but the effect is not strictly linear. The optimal runtime range appears to be approximately **120–160 minutes**.  

However, extremely long movies do not always guarantee higher ratings, suggesting diminishing returns beyond a certain point.  

---

## ⚠️ Limitations  

- Analysis does not include variables such as genre, budget, or director  
- Results depend on dataset quality and size  
- Future work could incorporate additional features for deeper insights  

---

## 🧾 Repository Structure  

- `optimal_movie_runtime_analysis.ipynb` → main analysis notebook  
- `data/` → dataset files (optional / ignored)  
- `figures/` → generated plots  

---

## 🤖 AI Usage  

This project was completed with assistance from AI tools (ChatGPT) for:
- structuring analysis  
- debugging code  
- improving explanations  

All outputs were reviewed and adapted by the author.
