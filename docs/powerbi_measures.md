# Power BI Measures

Assume the imported table is named:

`life_insurance_analysis_ready`

If Power BI imports the table with a different name, replace the table name in each formula.

## Core Measures

```DAX
Total Policyholders =
DISTINCTCOUNT(life_insurance_analysis_ready[customer_id])
```

```DAX
Priority 1 Policyholders =
CALCULATE(
    [Total Policyholders],
    life_insurance_analysis_ready[portfolio_priority_short] = "P1: High burden + exposure"
)
```

```DAX
Priority 1 % =
DIVIDE(
    [Priority 1 Policyholders],
    [Total Policyholders]
)
```

```DAX
Current Or Former Smokers =
CALCULATE(
    [Total Policyholders],
    life_insurance_analysis_ready[smoking_status] IN {"Current smoker", "Former smoker"}
)
```

```DAX
Current Or Former Smoker % =
DIVIDE(
    [Current Or Former Smokers],
    [Total Policyholders]
)
```

```DAX
Total Coverage =
SUM(life_insurance_analysis_ready[coverage_amount])
```

```DAX
Avg Coverage Amount =
AVERAGE(life_insurance_analysis_ready[coverage_amount])
```

```DAX
Avg Premium Burden % =
AVERAGE(life_insurance_analysis_ready[premium_to_income_ratio])
```

Format `Avg Premium Burden %` as Percentage in Power BI.

Do not format `premium_to_income_pct` directly as a percentage because that column already stores values like `2.29`, not `0.0229`.

## Recommended Action Column

```DAX
Recommended Action =
SWITCH(
    life_insurance_analysis_ready[portfolio_priority_short],
    "P1: High burden + exposure", "Advisor review + affordability and coverage-fit check",
    "P2: High burden", "Affordability review",
    "P3: High exposure", "Coverage exposure review",
    "P4: Elevated burden", "Monitor affordability burden",
    "P5: Elevated exposure", "Monitor coverage exposure",
    "Routine monitoring"
)
```

