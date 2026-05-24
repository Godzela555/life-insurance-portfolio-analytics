# Data Dictionary

The dataset is not included in the repository. This file documents the fields used in the notebook and dashboard.

## Identifier And Demographics

| Column | Meaning |
|---|---|
| `customer_id` | Unique policyholder identifier |
| `name` | Synthetic policyholder name |
| `age` | Policyholder age |
| `gender` | Gender category |
| `marital_status` | Marital status |
| `number_of_dependents` | Number of dependents |
| `annual_income` | Annual income |
| `occupation` | Occupation category |
| `health_status` | Health category |
| `smoking_status` | Smoking category |

## Policy And Premium Fields

| Column | Meaning |
|---|---|
| `policy_type` | Life insurance product type |
| `coverage_amount` | Insurance coverage amount |
| `monthly_premium` | Monthly premium |
| `policy_start_date` | Policy start date |
| `annual_premium` | Monthly premium multiplied by 12 |
| `policy_tenure_years` | Estimated policy tenure in years |
| `tenure_segment` | Tenure grouping |

## Business Ratios

| Column | Formula | Meaning |
|---|---|---|
| `premium_to_income_ratio` | `annual_premium / annual_income` | Affordability burden as a decimal ratio |
| `premium_to_income_pct` | `premium_to_income_ratio * 100` | Affordability burden as a readable percent value |
| `coverage_to_income_ratio` | `coverage_amount / annual_income` | Coverage exposure compared with income |
| `coverage_to_premium_ratio` | `coverage_amount / annual_premium` | Coverage supported per unit of annual premium |

## Segmentation Fields

| Column | Meaning |
|---|---|
| `affordability_risk` | Premium burden segment |
| `coverage_exposure` | Coverage exposure segment |
| `portfolio_priority` | Full priority segment label |
| `portfolio_priority_short` | Short dashboard priority segment |
| `income_segment` | Annual income band |
| `recommended_action` | Business action mapped from priority segment |

## Important Limitation

The dataset is synthetic and does not contain a real lapse, claim, or mortality target variable. The priority fields are business monitoring flags, not actual outcome labels.

