# University Test Scores Project

Statistical analysis of admissions, standardized test scores, tuition, and student income demographics across U.S. universities.

## Dataset
- **Source:** Kaggle — Christensen, Alexander P. *University Test Scores*. Kaggle, 2025. https://www.kaggle.com/datasets/alexsciences/university-test-scores
- **Topic:** Undergraduate admissions rates, SAT/ACT scores, enrollment, in-state/out-of-state tuition, funding type, US News Top 100 ranking, and the income-bracket makeup of admitted students.
- **Size:** 1,070 institutions, 14 cleaned variables (plus the original raw CSV with detailed SAT/ACT subscore columns).
- **Main research question:** How much do standardized test scores and other institutional factors (funding type, tuition, ranking, student income mix) relate to how selective a university's admissions process is?

## Folder Guide
- `assignment-02-dataset/` — Dataset selection, variable definitions, and sourcing (Assignment 2 write-up)
- `assignment-03-descriptive-stats/` — Descriptive statistics and frequency tables (Assignment 3)
- `assignment-04-probability/` — Probability distribution analysis (Assignment 4)
- `assignment-05-inference/` — Hypothesis tests and confidence intervals (Assignment 5)
- `assignment-06-regression/` — Multiple regression modeling (Assignment 6)
- `data` — Raw dataset file (CSV format)
- `DECISIONS.md` — Running log of key analysis decisions by assignment

## Team
Emily Bradley, with Benoit and Henry (Group 7). This analysis was completed as a team.

## Reflection
The most challenging part of this assignment wasn't the statistics — it was untangling a merge conflict in DECISIONS.md after my local repo and GitHub diverged. I'd never dealt with "divergent branches" before, and figuring out how to configure a merge strategy, resolve conflict markers by hand, and clear a stuck index.lock file taught me more about how Git actually tracks history than any tutorial had. Going forward, I plan to keep using this VS Code + GitHub workflow for every group project in the MSBA program — version control isn't just useful for code, it's the cleanest way for a team to build on each other's work without overwriting anyone's analysis, and having a real commit history and decision log makes it much easier to explain our reasoning later, whether that's to a professor or a future employer.
