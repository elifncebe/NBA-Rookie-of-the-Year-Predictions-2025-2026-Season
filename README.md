# 🏀 NBA Rookie of the Year
### Predicting the 2025–26 Rookie of the Year (ROY)

This project presents an end-to-end workflow for forecasting the NBA’s **Rookie of the Year (ROY)** using publicly available historical data from the official NBA Stats API (`nba_api`). The goal is to build a reproducible and data-driven model that identifies which rookies in a target season are most likely to win the award.

### Project Objectives
1. Collect historical rookie performance metrics from the 2010–11 through 2023–24 seasons.  
2. Label each season’s Rookie of the Year to create a supervised learning target.  
3. Engineer meaningful features (scoring, usage, efficiency, defensive impact, and team context).  
4. Train a statistical model to estimate the probability that a rookie becomes ROY.  
5. Apply the model to the **2025–26** rookie class and generate a ranked list of candidates.  
6. Export the required **`predictions.csv`** file containing:
   - `player_name`
   - `probability` (value between 0 and 1)

### Modeling Philosophy
The aim is **not** to predict ROY with perfect accuracy; the award is subjective and influenced by narrative and voting dynamics. Instead, the model serves as a **ranking tool**—highlighting which rookies’ profiles most resemble prior ROY winners based on measurable on-court impact.

### Reproducibility
This notebook runs cleanly end-to-end using only:
- `nba_api`  
- `pandas`  
- `numpy`  
- `scikit-learn`

All steps, transformations, and modeling decisions are documented in the notebook.

### Setup & Dependencies
To run this notebook, you need to install the following Python packages:

```bash
pip install nba_api pandas numpy scikit-learn tqdm
```

### Data Sources
Historical rookie performance metrics are collected from the NBA Stats API via the `nba_api` library.
ROY winners for each season are manually curated.

### Model
A logistic regression model is used to predict the probability of a rookie winning the ROY award. Features include various per-game statistics like points, rebounds, assists, steals, blocks, efficiency metrics, and team win percentage. The features are standardized using `StandardScaler`.

### Predictions
The trained model is applied to the 2025–26 rookie class to generate probability scores for each player. The output is a ranked list of candidates, saved to `predictions.csv`.

### Conclusion
This project provides a robust and reproducible framework for ranking NBA ROY candidates based on historical performance patterns. The generated `predictions.csv` file offers insights into potential future ROY winners.

### Citations & External Resources
- **NBA Stats API Documentation**: https://github.com/swar/nba_api
- **NBA Glossary**: https://www.nba.com/stats/help/glossary
- **pandas**: https://pandas.pydata.org/
- **Scikit-learn**: https://scikit-learn.org/
- **Applied Logistic Regression** by Hosmer, D. W., Lemeshow, S.
- **Learning from Imbalanced Data** by He, H., Garcia, E. A.
- **Stack Overflow**: https://stackoverflow.com/
- **Basketball Reference**: https://www.nba.com/news/history-rookie-of-the-year-winners
