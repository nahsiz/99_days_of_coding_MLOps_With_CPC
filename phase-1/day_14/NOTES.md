# Day 14 — Three-Column Correlation Analysis with Shared X-Axis

## What I Built

- Loaded the FuelConsumption dataset and cleaned column names with `.str.strip()`.
- Selected one shared x-axis column (ENGINE SIZE) and three y-axis columns (FUEL CONSUMPTION, COEMISSIONS, CYLINDERS).
- Calculated three Pearson correlation coefficients against the shared x column.
- Created a 4×4 correlation heatmap.
- Created three scatter plots with regression lines, all sharing the same x-axis (ENGINE SIZE).
- Interpreted all three correlation coefficients.

## Key Findings

1. ENGINE SIZE was used as the shared x-axis for all three comparisons.
2. Three Pearson correlations: ENGINE SIZE vs FUEL CONSUMPTION, ENGINE SIZE vs COEMISSIONS, ENGINE SIZE vs CYLINDERS.
3. All scatter plots share the same x-axis, making them directly comparable.
4. The heatmap revealed correlations among all four selected columns.

## Tools Used

- Python, Pandas, NumPy, Matplotlib, Seaborn
