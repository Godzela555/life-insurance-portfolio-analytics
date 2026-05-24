# Dashboard Field Map

This document explains which fields are used in the Power BI dashboard.

## Recommended Display Names

| Source Column | Dashboard Display Name |
|---|---|
| `customer_id` | Policyholder ID |
| `portfolio_priority_short` | Priority Segment |
| `premium_to_income_ratio` | Premium Burden |
| `coverage_to_income_ratio` | Coverage-to-Income |
| `coverage_amount` | Coverage Amount |
| `monthly_premium` | Monthly Premium |
| `annual_premium` | Annual Premium |
| `income_segment` | Income Segment |
| `policy_type` | Policy Type |
| `smoking_status` | Smoking Status |
| `marital_status` | Marital Status |
| `recommended_action` | Recommended Action |

## Slicers

| Slicer | Column |
|---|---|
| Policy Type | `policy_type` |
| Smoking Status | `smoking_status` |
| Gender | `gender` |
| Income Segment | `income_segment` |
| Marital Status | `marital_status` |

## KPI Cards

| Card | Field or Measure |
|---|---|
| Total Policyholders | `Total Policyholders` |
| Priority 1 Policyholders | `Priority 1 Policyholders` |
| Current or Former Smoker % | `Current or Former Smoker %` |
| Priority 1 % | `Priority 1 %` |
| Total Coverage | `Total Coverage` |
| Average Premium Burden | `Avg Premium Burden %` |

## Main Visuals

| Visual | Fields |
|---|---|
| Policyholders by Priority Segment | `portfolio_priority_short`, count of `customer_id` |
| Priority 1 Matrix | `policy_type`, `income_segment`, count of `customer_id`, filtered to Priority 1 |
| Policy Type Mix | `portfolio_priority_short`, `policy_type`, count of `customer_id` |
| Average Coverage | `portfolio_priority_short`, average of `coverage_amount` |
| Average Premium Burden | `portfolio_priority_short`, `Avg Premium Burden %` |
| Customer Watchlist | `customer_id`, `policy_type`, `income_segment`, `annual_income`, `monthly_premium`, `premium_to_income_pct`, `coverage_amount`, `coverage_to_income_ratio`, `smoking_status`, `health_status`, `recommended_action` |

