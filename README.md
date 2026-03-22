# Predicting Human Decision-Making Under Risk Using Machine Learning

## Overview

This project focuses on predicting human decision-making under uncertainty using the choices13k dataset.

Participants were presented with two risky options (Gamble A and Gamble B), and the goal is to predict `bRate`, the proportion of times participants chose Gamble B.

The task combines behavioral science and machine learning to model how people evaluate risk, reward, and uncertainty.

---

## Objective

Given two gambles defined by probabilistic outcomes, build a model that predicts:

bRate - how often people choose Gamble B over Gamble A

---

## Repository Structure

```
.
├── solution.ipynb
├── assignment_brief.ipynb
├── c13k_selections.csv
├── c13k_problems.json
└── README.md
```

---

## Dataset Description

### c13k_selections.csv

Contains:

* Gamble identifiers
* Observed choice frequencies (bRate)
* Additional experimental variables

### c13k_problems.json

Defines:

* Outcomes and probabilities for each gamble
* Structure of Gamble A and Gamble B

---

## Methodology

### Data Preparation

* Merged CSV and JSON datasets
* Parsed gamble structures into numerical representations
* Cleaned and aligned all inputs

---

### Feature Engineering

Each gamble is transformed into descriptive numerical features.

Individual gamble features include:

* Expected value
* Variance and standard deviation
* Skewness
* Minimum and maximum outcomes
* Probability of gains, losses, and zero outcomes
* Entropy (uncertainty)
* Semi-variance (downside risk)
* Expected shortfall (tail risk)

Comparative features between Gamble B and Gamble A include:

* Differences between key statistics
* Stabilized ratios
* Absolute differences
* Dominance indicators

These features capture behavioral aspects such as risk sensitivity, loss aversion, and reward comparison.

---

### Models Used

The following models were implemented and compared:

* Random Forest
* XGBoost
* Support Vector Regression (SVR)
* Multi-Layer Perceptron (Neural Network)

---

### Training Setup

* Train/test split: 80/20
* Cross-validation: 3-fold
* Hyperparameter tuning applied
* Model selection based on cross-validated MAE

---

## Evaluation Metrics

* Mean Absolute Error (MAE) as the primary metric
* Root Mean Squared Error (RMSE)
* R² score

---

## Results

### Best Model: XGBoost

| Metric | Cross-Validation | Test Set |
| ------ | ---------------- | -------- |
| MAE    | 0.0645           | 0.0621   |
| RMSE   | 0.0853           | 0.0838   |
| R²     | 0.8523           | 0.8566   |

---

## Feature Importance

The most influential predictors include:

* Dominance relationships between gambles
* Expected value differences
* Value-to-risk trade-offs
* Downside risk measures
* Gain/loss asymmetry features
* Ambiguity-related variables

These findings are consistent with behavioral theories of decision-making under risk.

---

## Conclusion

The results show that human choice behavior in risky decision problems can be predicted with good accuracy using engineered features and machine learning models.

Among the evaluated approaches, XGBoost achieved the strongest performance and generalized well to unseen data.

---

## How to Run

1. Open `solution.ipynb` in Jupyter Notebook, JupyterLab, or VS Code
2. Ensure all dataset files are in the same directory
3. Run all cells

---

## Author

Panagiota Machaira
Student ID: p3210119

