# Day 16 — Three-Column Correlation Analysis with Shared X-Axis

## What I Built

- Loaded the Air Pollution dataset and cleaned column names with .str.strip() 
- Selected one shared x-axis column (Temperature) and three y-axis columns (PM2.5, PM10, CO).
- Calculated three Pearson correlation coefficients against the shared x column.
- Created a 4×4 correlation heatmap.
- Created three scatter plots with regression lines, all sharing the same x-axis (Temperature).
- Interpreted all three correlation coefficients.

## Key Findings

1. Temperature was used as the shared x-axis for all three comparisons.
2. Three Pearson correlations: Temperature vs PM2.5, Temperature vs PM10, Temperature vs CO.
3. All scatter plots share the same x-axis, making them directly comparable.
4. The heatmap revealed correlations among all four selected columns.

## Tools Used

- Python, Pandas, NumPy, Matplotlib, Seaborn
