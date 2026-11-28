# Day 19 — Four-Column Correlation, Data Quality & Findings

**Dataset:** World Happiness Report 2015 (158 countries)
**Shared X-Axis:** Economy (GDP per Capita)
**Y-Columns:** Happiness Score, Health (Life Expectancy), Freedom

---

## Three Findings

1. **Strongest correlation with the target.**
   Among the three y-columns compared against GDP per capita, **Happiness Score** shows the strongest positive correlation (~0.80), followed by **Health (Life Expectancy)** (~0.75), while **Freedom** shows the weakest relationship (~0.35). This means GDP per capita is a strong linear predictor of a country's overall happiness and life expectancy, but a much weaker predictor of perceived freedom.

2. **Skewed / spiky histograms.**
   - Economy (GDP per Capita) is **heavily right-skewed** (positive skew, ~1.0+) — most countries cluster between 0.3 and 1.3, with a long tail of high-GDP outliers (Qatar, Luxembourg, Singapore, Kuwait, Norway).
   - Happiness Score is **left-skewed** (negative skew) with most countries in the 5–7 range and a small tail of low-happiness countries (Burundi, Togo, Syria, Benin, Rwanda).
   - Health (Life Expectancy) shows a **bimodal-like shape** — a large cluster of high life-expectancy countries (>0.85) and a smaller cluster of low ones (<0.5).
   - Freedom is roughly symmetric around 0.4–0.5, with only a mild right skew.

3. **Data quality — IQR outliers in GDP.**
   Using the IQR method on Economy (GDP per Capita), only a handful of countries (Qatar, Luxembourg, Singapore, Kuwait, Norway, Switzerland, UAE, Brunei) fall above the upper IQR bound. These are **legitimate extreme values**, not errors — but they pull the regression line slightly upward in the scatter plots and inflate the Pearson correlation coefficient. Removing them would reduce the correlation strength noticeably.

---

## One Data Quality Issue

**The Dystopia Residual column is a derived residual, not a raw measurement.**
It is the leftover after all other predictors (GDP, Family, Health, Freedom, Trust, Generosity) are used to explain Happiness Score — so by construction it is **mathematically coupled** with Happiness Score and with the other predictors. It should **not** be treated as an independent feature in any modelling or correlation analysis.

**Decision:** It was **excluded** from the selected four columns. If a future analysis includes it, the results will be tautological and not meaningful.

(Secondary quality note: some columns like Trust (Government Corruption) contain 0 values that may represent missing data rather than genuine zero trust — flagged but not modified here.)

---

## Three Lines

- **What I built:** A 4-column Pearson correlation analysis with a shared x-axis (Economy GDP per Capita), a 4×4 correlation heatmap, three scatter plots with regression lines, four histograms with skewness values, and complete data quality checks (missing values, duplicate rows, IQR outliers on GDP).
- **What broke:** Nothing broke technically, but the strong GDP vs Happiness correlation (~0.80) is **partly tautological** because Dystopia Residual — excluded from our four columns — is constructed from the other predictors to make the model fit. Also, Freedom had a much weaker correlation than expected, so the regression line in that scatter plot was visibly flatter.
- **What I learned:** How to run a full data quality pass (missing, duplicates, IQR) alongside correlation analysis; how to detect skewness from histograms and confirm it numerically; and why derived/residual columns (Dystopia Residual) must be inspected and excluded before analysis — otherwise Pearson correlation produces misleadingly strong numbers.

---

## What I Built (extended)

- Loaded the World Happiness Report 2015 dataset using Pandas.
- Checked shape, dtypes, missing values, duplicate rows, and GDP outliers with the IQR method.
- Selected one shared x-axis column (GDP per Capita) and three y-columns (Happiness Score, Health, Freedom).
- Calculated three Pearson correlations against GDP per capita.
- Built a 4×4 correlation heatmap.
- Built three scatter plots with regression lines, all sharing the same x-axis (GDP per capita).
- Built four histograms to detect skew and spikes, with skewness printed numerically.
- Wrote three findings, one data quality issue, and the three required lines.

## Tools Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
