# Decision Log

## Assignment 2: Dataset (2026-07-19)
- Dataset: University Test Scores from Kaggle (Christensen, Alexander P. *University Test Scores*. Kaggle, 2025. https://www.kaggle.com/datasets/alexsciences/university-test-scores)
- Main variable of interest: Admissions Rate because it captures how selective a school is, and lets us test how much standardized test scores actually factor into admissions decisions
- Key decision: Build one categorical variables (USnewsTop100Rank) alongside the continuous variables so we could compare admissions/test-score patterns across ranked vs. unranked schools

## Assignment 3: Descriptive Stats (2026-07-26)
- Cleaning done: Created new categorical variable using US NEWS Top 100 Rankings (Top 50, Ranked 51-100, Unranked)
- Most surprising pattern: Total_Undergraduates is heavily right-skewed (skewness 3.02, kurtosis 11.5). A few very large universities pull the mean (5,597) far above the median (2,429). Admissions_Rate is left-skewed the opposite way, with most schools clustered at high acceptance rates (70-93%) rather than being highly selective. 

## Assignment 4: Probability (2026-07-26)
- Normal vs. empirical, and why: Only SAT_Average, median ACT_Composite_50, the $30-48K income bracket (Income_2_Percent), and (weakly) public out-of-state tuition were close to a normal distribution. Total_Undergraduates, tuition variables, Admissions_Rate, and the other income brackets were too skewed for normal-based probability, so empirical/percentile-based probabilities were used for those instead.

## Assignment 5: Inference (2026-08-09)
- What we tested, alpha, conclusion: Ran two one-sample t-tests at α = 0.05.
  1. H0: mean Admissions_Rate ≥ 50% vs. Ha: < 50% → failed to reject (t = 25.84, p = 1.0). Assuming 50% acceptance rate can be categorized as a selective admissions to an institution, most universities in the dataset are not selective.
  2. H0: mean SAT_Average ≤ 1029 vs. Ha: > 1029 → rejected H0 (t = 33.14, p ≈ 0). The average SAT composite in our dataset is significantly higher than the national Class of 2025 average of 1029. 
  - Also built a 95% CI for average in-state public tuition: $22,285.49–$24,107.89.
    - Filtered datatset into public and private universities (private universitites have the same in-state and out-of-state tuition prices)

## Assignment 6: Regression (2026-08-13)
- First predictor removed and why: Income_3_Percent, removed from Model 1 for the highest p-value (p = 0.863) of any predictor. R² barely moved (0.621 → 0.621), confirming it added little explanatory power.
- Multicollinearity handling: Checked pairwise correlations among predictors prone to overlap (ACT_Composite_50, Total_Undergraduates, OutState_Tuition, Income_1/2/5_Percent) before finalizing the model. Predictors were then dropped one at a time by highest p-value — Income_3_Percent, then rank_new (p = 0.698), then Admissions_Rate (p = 0.386) — landing on a Final Model with SAT_Average, ACT_Composite_50, Total_Undergraduates, OutState_Tuition, Income_1_Percent, Income_2_Percent, and Income_5_Percent (R² = 0.620, Adjusted R² = 0.613).
- SAT_average and ACT_Composite_50 were highly correlated along with the income variables
  - Further models would require either SAT_average or ACT_Composite_50 to be removed along with 2 of the income variables to account for multicollinearity
