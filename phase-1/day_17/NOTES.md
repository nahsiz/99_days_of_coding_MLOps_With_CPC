# Day 17 — Three-Column Correlation Analysis with Shared X-Axis

## What I Built

- Loaded the HR Employee Attrition dataset and cleaned column names with .str.strip()  and BOM removal.
- Selected one shared x-axis column (Age) and three y-axis columns (MonthlyIncome, TotalWorkingYears, YearsAtCompany).
- Calculated three Pearson correlation coefficients against the shared x-axis column.
- Created a 4×4 correlation heatmap.
- Created three scatter plots with regression lines, all sharing the same x-axis (Age).
- Interpreted all three correlation coefficients.

## Key Findings

1. Age was used as the shared x-axis for all three comparisons.
2. Three Pearson correlations: Age vs MonthlyIncome, Age vs TotalWorkingYears, Age vs YearsAtCompany.
3. All scatter plots share the same x-axis, making them directly comparable.
4. The heatmap revealed correlations among all four selected columns.

## Tools Used

- Python, Pandas, NumPy, Matplotlib, Seaborn
