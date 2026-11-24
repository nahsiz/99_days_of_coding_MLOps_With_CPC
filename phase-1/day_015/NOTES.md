# Day 15 — Three-Column Correlation Analysis with Shared X-Axis

## What I Built

- Loaded the Student Mental Health dataset and cleaned column names with .str.strip()
- Encoded the three Yes/No mental health columns (Depression, Anxiety, Panic attack) into 0/1 numeric values.
- Dropped rows where Age was missing.
- Selected one shared x-axis column (Age) and three y-axis columns (Depression, Anxiety, Panic attack).
- Calculated three Pearson correlation coefficients against the shared x column.
- Created a 4×4 correlation heatmap.
- Created three scatter plots with regression lines, all sharing the same x-axis (Age).
- Interpreted all three correlation coefficients.

## Key Findings

1. Age was used as the shared x-axis for all three comparisons.
2. Three Pearson correlations: Age vs Depression, Age vs Anxiety, Age vs Panic attack.
3. All scatter plots share the same x-axis, making them directly comparable.
4. The heatmap revealed correlations among all four selected columns.
5. Yes/No columns were encoded to 1/0 before correlation because Pearson correlation requires numeric input.

## Tools Used

- Python, Pandas, NumPy, Matplotlib, Seaborn
