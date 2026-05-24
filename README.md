# Life Insurance Portfolio Analytics

## Project Overview

This project analyzes a synthetic life insurance policyholder dataset and builds a one-page Power BI monitoring dashboard for portfolio review.

The dashboard focuses on identifying policyholder groups that may need business attention based on premium affordability burden, coverage exposure, income segment, policy type, and smoking status.

## Live Dashboard

Published Power BI report:

https://app.powerbi.com/groups/me/reports/1bb2deff-3ef5-45ef-841e-4350a972fc89/26cab50330211eb9d562?experience=power-bi

If the live link requires permission, use the dashboard PDF preview:

`dashboard/insurance_dashboard.pdf`

## Data 

Dataset source:

https://www.kaggle.com/datasets/ayushyajnik/life-insurance-retention-dataset

## Business Questions

- Which policyholders have high premium affordability burden?
- Which policyholders have high coverage exposure compared with income?
- Which customers should be prioritized for advisor review?
- Are high-priority customers concentrated in specific policy types or income segments?
- How can the portfolio be monitored in Power BI?

## Tools Used

- Python
- Pandas
- Matplotlib
- Seaborn
- Power BI

## Key Metrics

- Total policyholders
- Priority 1 policyholders
- Priority 1 percentage
- Current or former smoker percentage
- Total coverage amount
- Average premium burden
- Average coverage amount
- Policy type mix
- Income segment mix

## Priority Logic

The dashboard uses rule-based portfolio priority segments.

Premium burden:

`annual_premium / annual_income`

Coverage exposure:

`coverage_amount / annual_income`

Priority segments:

- `P1: High burden + exposure`
- `P2: High burden`
- `P3: High exposure`
- `P4: Elevated burden`
- `P5: Elevated exposure`
- `Routine`

This is not a predictive lapse model. It is a transparent business-monitoring framework for prioritizing review.

## Main Findings

- The portfolio contains 10,000 synthetic policyholders.
- Priority 1 contains 348 policyholders, or 3.48% of the portfolio.
- Current or former smokers represent 21.06% of policyholders.
- Total coverage is approximately 3.68 billion.
- Average premium burden is approximately 2.29% of annual income.
- High-priority customers are concentrated more heavily in lower income segments.
- Universal Life and Whole Life appear more frequently in high-priority segments than in the routine segment.

## Business Recommendations

- Review Priority 1 customers first because they combine high affordability burden and high coverage exposure.
- Use affordability review for customers with high premium-to-income ratios.
- Use coverage-fit review for customers with high coverage-to-income ratios.
- Monitor Universal Life and Whole Life segments closely because they are more represented in higher-priority groups.
- Use dashboard filters to review policyholders by policy type, income segment, gender, marital status, and smoking status.

## Repository Contents

```text
dashboard/
  insurance_dashboard.pdf

notebooks/
  Insurance_Project.ipynb

docs/
  dashboard_field_map.md
  data_access.md
  data_dictionary.md
  powerbi_measures.md
  upload_checklist.md
```

## How To Run The Notebook

Install dependencies:

```bash
pip install -r requirements.txt
```

Open and run:

```text
notebooks/Insurance_Project.ipynb
```

The notebook uses `kagglehub` to download the public Kaggle dataset.

## Limitations

- The main policyholder dataset is synthetic.
- The dataset does not include actual lapse, claim, or mortality outcomes.
- The priority segments are rule-based business flags, not actuarial pricing or underwriting decisions.
- The Power BI `.pbix` file is not included because it may contain an imported copy of the dataset.

