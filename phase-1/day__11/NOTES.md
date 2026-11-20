# Day 11 — Multi-Column Correlation Analysis with Shared X-Axis

## What I Built

- Loaded the Car Price dataset using Pandas.
- Selected one shared x-axis column (Year) and two y-axis columns (Selling_Price, Kms_Driven).
- Calculated two Pearson correlation coefficients, both using Year as the shared x column.
- Created a 3×3 correlation heatmap for the three selected columns.
- Created two scatter plots with regression lines, both sharing the same x-axis (Year).
- Generated individual histograms for all three selected columns.
- Used two joint plots to visualize each pair with individual distributions.
- Interpreted both correlation coefficients to identify the direction of each linear relationship.

## What I Learned

- How to fix the x-axis and change the y-axis across multiple correlation plots.
- How to compute correlation between one shared column and multiple target columns.
- How to build a 3×3 correlation heatmap that captures both pairs at once.
- How to compare a positive linear relationship and a negative linear relationship side by side.
- How to visualize two feature pairs using the same horizontal axis.

## Key Findings

1. The analysis used Year as the shared x-axis column for both comparisons.
2. Two Pearson correlation coefficients were computed: Year vs Selling_Price and Year vs Kms_Driven.
3. Both scatter plots and joint plots share the same x-axis (Year), making them directly comparable.
4. The heatmap also revealed the correlation between Selling_Price and Kms_Driven themselves.
5. Both correlations were interpreted using the same if / elif / else pattern from Day 9 and Day 10.

## Data Quality Check

- Selected columns were checked for missing values.
- Numerical data types were confirmed before correlation analysis.
- The selected data was inspected before visualization.

## Limitations

- Only three columns were selected for this analysis.
- Correlation does not imply causation.
- Pearson correlation captures only linear relationships, not nonlinear patterns.

## Tools Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
