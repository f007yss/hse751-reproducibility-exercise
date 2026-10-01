# Diabetes Risk Factor Analysis

HSE 751 Reproducibility Exercise. Jeremy Childress.

Colab notebook: https://colab.research.google.com/drive/1cWvrR_g4QRgYL-UnhpRV8252ZaXumhi9?usp=sharing

## Purpose

Compares clinical measurements between patients with and without diabetes, in a notebook another team can rerun or reuse with their own data.

The analysis covers data validation, recoding missing values, descriptive statistics, four plots, a Spearman correlation heatmap, a Welch t-test (glucose), and a Mann-Whitney U test (BMI).

## Files

- `diabetes_risk_factor_analysis_Childress.ipynb` is the notebook
- `Example Dataset_Diabetes.csv` is the data
- `requirements.txt` lists the packages
- `reproducibility_summary.md` is the reproducibility summary

## Data

Pima Indians Diabetes Database, originally from NIDDK and publicly available on UCI and Kaggle. This copy comes from the HSE 751 course repo. It has 768 female patients, age 21 or older.

The file must be named `Example Dataset_Diabetes.csv` and have these columns:
`Pregnancies, Glucose, D_BP, Skin_Thickness, Insulin, BMI, Pedigree, Age, Outcome`

## Environment

Tested in Google Colab.

- Python 3.13.15
- pandas 2.2.3
- numpy 2.1.3
- matplotlib 3.10.0
- seaborn 0.13.2
- scipy 1.16.3

To run locally, use `pip install -r requirements.txt`.

## How to Run

1. Open the notebook in Colab.
2. Upload the CSV in the Files pane. If you skip this, the notebook prompts for it.
3. Runtime > Restart session and run all.

## Expected Outputs

- Welch t-test: t = 14.88, p ≈ 2.8e-41
- Mann-Whitney U: U = 89731, p ≈ 1.8e-17
- Bootstrap mean BMI: 32.36

If your results match these, the run reproduced.

## Assumptions and Limitations

- Zeros in Glucose, D_BP, Skin_Thickness, Insulin, and BMI are treated as missing. Insulin is missing for about half of patients.
- Incomplete rows are kept. Each analysis uses the available values.
- Random steps use seed 42.
- The sample is narrow, so results may not generalize.
- The results are associations, not causes.
