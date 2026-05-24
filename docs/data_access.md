# Data Access

Data files are not included in this repository.

The notebook downloads the source dataset directly from Kaggle:

https://www.kaggle.com/datasets/ayushyajnik/life-insurance-retention-dataset

## Why The Data Is Excluded

The repository is designed to show the analysis, notebook output, dashboard design, and business reasoning without redistributing dataset files.

The following files should not be uploaded:

- raw CSV files
- analysis-ready CSV files
- Excel exports
- Power BI `.pbix` files that contain imported data
- interactive HTML dashboard exports that embed row-level data

## Reproducing The Analysis

Install the requirements:

```bash
pip install -r requirements.txt
```

Then run:

```text
notebooks/Insurance_Project.ipynb
```

The notebook uses:

```python
import kagglehub

path = kagglehub.dataset_download("ayushyajnik/life-insurance-retention-dataset")
```

