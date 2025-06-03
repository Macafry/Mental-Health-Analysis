# 🧠 Anxiety in Context

## 📌 Overview

This project explores patterns in self-reported anxiety levels using a [synthetic dataset](https://www.kaggle.com/datasets/natezhang123/social-anxiety-dataset). It implements a **stacked modeling approach** to distinguish between **low-to-moderate (1–7)** and **high anxiety (8–10)**, combining logistic and linear regression models.

The analysis prioritizes interpretability, model diagnostics, and actionable insights. The full write-up is available as a Quarto website:  
🔗 **[Anxiety in Context](https://macafry.github.io/Mental-Health-Analysis/)**

---

## 🧪 Methodology

1. **Exploratory Data Analysis**  
   Investigated variable distributions, missingness, and correlations. Identified strong signals in stress and sleep quality. And motivated a stacked modeling approach to separate low-to-moderate from high anxiety.

2. **Modeling Low/Moderate vs High Anxiety**  
   Used logistic regression to flag individuals at high risk (8–10). Demonstrated strong performance and interpretability.

3. **Modeling Low/Moderate Anxiety (1–7)**  
   Compared linear and ordinal logistic regression. Linear model was favored for clarity and robustness.

4. **Modeling High Anxiety Separately**  
   Analyzed the distinct response patterns in high anxiety cases, justifying separate treatment due to skew and tail behavior.

---

## 📊 Key Results

- **Stress** and **sleep** are the strongest predictors of anxiety.
- **Therapy attendance** is associated with high anxiety — likely a result of reverse causality.
- **Linear regression** handles ordinal responses reasonably well and offers strong interpretability.
- **Logistic regression** effectively identifies high-anxiety individuals with minimal false positives.

---

## 📦 Requirements

Install all required libraries using:

```r
install.packages(c(
  "car", "caret", "DT", "e1071", "flexplot", "htmltools", "infotheo",
  "knitr", "MASS", "partykit", "patchwork", "pomcheckr", "pROC",
  "RColorBrewer", "ranger", "tidyverse"
))
```
-----


## Project stucture 

```
.
├── data/
│   └── enhanced_anxiety_dataset.csv        # Input dataset
├── statistical_supplements/
│   ├── exploratory_data_analysis.qmd       # Visual and statistical EDA
│   ├── low_to_moderate_regression.qmd      # Modeling anxiety 1–7
│   ├── high_anxiety.qmd                    # Explaining 8–10 modeling challenges
│   ├── low-mod_vs_high_logisitc.qmd        # Binary logistic model (8–10 vs others)
├── index.qmd                               # General audience report
└── reflection.qmd                          # Author's reflection
```

## Running the Analysis

You can either:
- Open .qmd files in RStudio and run interactively.
- Run `quarto render` on the root directory to render the full website.
