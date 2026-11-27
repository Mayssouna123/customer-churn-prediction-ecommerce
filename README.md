# Customer Churn Prediction in E-Commerce

## Project Overview

This project develops a machine learning approach to identify e-commerce customers who are at risk of becoming inactive. It uses transaction history, RFM analysis, classification models, and SHAP explainability to support customer retention decisions.

## Dataset

The project uses the Online Retail dataset.

- Source: [Kaggle – E-Commerce Data](https://www.kaggle.com/datasets/carrie1/ecommerce-data)
- Original source: UCI Machine Learning Repository
- The raw dataset is not included in this repository. Download it separately and place it in the project root as `data.csv`.

## Methodology

The project includes:

1. Data exploration and cleaning
2. RFM feature engineering
3. Exploratory data analysis
4. Stratified training, validation, and test splitting
5. Baseline classification
6. Random Forest and XGBoost modelling
7. Class imbalance handling
8. Validation-based threshold selection
9. Customer risk segmentation
10. SHAP-based model interpretation
11. Illustrative retention campaign and ROI analysis

The prediction target identifies customers who made no qualifying purchase during the 90-day period from September 1 to November 29, 2011. This represents purchase inactivity, not confirmed permanent churn.

## Final Test Results

The selected XGBoost model achieved the following results on the held-out test set:

| Metric | Result |
|---|---:|
| Accuracy | 64.31% |
| Precision | 57.22% |
| Recall | 73.54% |
| F1-score | 64.36% |
| ROC-AUC | 0.71 |
| Average Precision | 0.59 |

The classification threshold was selected using the validation set.

## Model Interpretability

SHAP analysis was used to examine the features contributing most to model predictions. Frequency, purchase activity span, and recency were among the most influential features.

## Business Analysis

Customers were grouped into low-, medium-, and high-risk segments using their predicted probabilities.

The project also includes hypothetical retention campaign scenarios. These ROI estimates are illustrative and depend on the assumptions stated in the report; they are not measured campaign results.

## Project Structure

- `notebooks/` – Data exploration and modelling notebooks
- `models/` – Saved model and metadata
- `outputs/` – Generated project outputs
- `reports/` – Final academic report and evaluation summaries
- `requirements.txt` – Python dependencies
- `.gitignore` – Files excluded from version control

## How to Run

1. Clone or download this repository.
2. Install the required dependencies:

   `pip install -r requirements.txt`

3. Download the dataset and place `data.csv` in the project root.
4. Open the notebook in the `notebooks/` directory.
5. Run the notebook cells from beginning to end.

## Limitations

The target measures inactivity within a defined observation window rather than permanent customer churn. The dataset represents one retailer and a limited historical period. Missing customer identifiers, duplicate transaction records, feature correlations, and the absence of temporal validation should also be considered when interpreting the results.

The risk probabilities are not calibrated estimates of actual churn probability. The ROI analysis is based on hypothetical assumptions.

## Reference

Chen, D. (2015). *Online Retail*. UCI Machine Learning Repository.  
https://doi.org/10.24432/C5BW33
