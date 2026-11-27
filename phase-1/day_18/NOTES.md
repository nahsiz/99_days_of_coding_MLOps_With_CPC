# Day 18 — Four-Column Correlation, Data Quality & Findings

**Dataset:** Diabetes Health Indicators (BRFSS2015)
**Shared X-Axis:** BMI
**Y-Columns:** Diabetes_012, GenHlth, Age

---

## Three Findings

1. **Strongest correlation with the target.**
   Among the three y-columns compared against BMI, **GenHlth** shows the strongest (positive) correlation with BMI, followed by **Diabetes_012**, and **Age** shows the weakest relationship. This suggests BMI is a stronger linear indicator of general health status and diabetes than of age group in this dataset.

2. **Skewed / spiky histograms.**
   - `BMI` is **right-skewed** (positive skew) with a long tail on the high end and a small spike of extreme BMI values — a few records sit far beyond the IQR upper bound.
   - `Diabetes_012` is **heavily imbalanced** — the vast majority of rows are `0.0` (no diabetes), with very few `1.0` (prediabetes) and `2.0` (diabetes). This is visible as a single tall spike at 0 in the histogram.
   - `GenHlth` and `Age` are **ordinal/categorical**, so their histograms show discrete bar-shaped bands rather than a smooth distribution.

3. **Data quality — outliers in BMI.**
   Using the IQR method on `BMI`, a noticeable number of rows (~5–7% of the dataset) fall outside the lower/upper IQR bounds. These extreme BMI values distort scatter plots and pull the Pearson correlation slightly away from the true linear trend. A follow-up fix would be to either cap (winsorize) or drop these rows before training a model.

---

## One Data Quality Issue

**Duplicate rows.**
The dataset contains a very large number of **duplicate rows** (health survey records that are identical across all 22 columns). Since the survey is anonymous, these cannot be safely removed without losing potentially valid responses from different individuals — but they do inflate the size of the dataset and can **bias the correlation coefficients** toward the most common combinations (especially the `0.0` diabetes class).

**Decision:** Duplicates were counted and reported, but **not dropped**, because in an anonymous health survey they may represent different respondents with identical answers. Any downstream model built on this dataset should treat duplicates as a known limitation.

---

## Three Lines

- **What I built:** A 4-column Pearson correlation analysis with a shared x-axis (BMI), a 4×4 correlation heatmap, three scatter plots with regression lines, histograms with skewness values, and complete data quality checks (missing values, duplicates, outliers).
- **What broke:** Nothing broke during the run — but the `Diabetes_012` and `GenHlth` scatter plots looked "banded" instead of showing a clean linear cloud, because these columns are categorical (0/1/2 and 1–5), not continuous. Pearson correlation still worked, but its value is only meaningful as a rough direction indicator here.
- **What I learned:** How to combine a correlation analysis with real data quality checks, how IQR-based outlier detection works, how to read skewness from a histogram, and why duplicate rows in an anonymous survey can't be blindly dropped — they have to be documented as a limitation.

---

## What I Built (extended)

- Loaded the Diabetes Health Indicators dataset using Pandas.
- Checked shape, dtypes, missing values, duplicate rows, and BMI outliers with the IQR method.
- Selected one shared x-axis column (BMI) and three y-columns (Diabetes_012, GenHlth, Age).
- Calculated three Pearson correlations against BMI.
- Built a 4×4 correlation heatmap.
- Built three scatter plots with regression lines, all sharing the same x-axis (BMI).
- Built four histograms to detect skew and spikes.
- Wrote three findings, one data quality issue, and the three required lines.

## Tools Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
