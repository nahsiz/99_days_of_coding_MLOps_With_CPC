# Day 13 — Four-Column Correlation Analysis with Shared X-Axis

## What I Built

- Loaded the E-commerce Customer Behavior dataset using Pandas.
- Selected one shared x-axis column (age) and three y-axis columns (website_visits, purchase_frequency, total_spend).
- Calculated three Pearson correlation coefficients, all using age as the shared x column.
- Created a 4×4 correlation heatmap for the four selected columns.
- Created three scatter plots with regression lines, all sharing the same x-axis (age).
- Generated individual histograms for all four selected columns.
- Used three joint plots to visualize each pair with individual distributions.
- Interpreted all three correlation coefficients to identify the direction of each linear relationship.

## What I Learned

- How to extend the shared x-axis pattern from two features to three features.
- How to compute multiple correlations against one shared column.
- How to build a 4×4 correlation heatmap that captures all pairs at once.
- How to compare three linear relationships side by side using the same horizontal axis.
- How to visualize three feature pairs using the same x-axis.

## Key Findings

1. The analysis used age as the shared x-axis column for all three comparisons.
2. Three Pearson correlation coefficients were computed: age vs website_visits, age vs purchase_frequency, and age vs total_spend.
3. All scatter plots and joint plots share the same x-axis (age), making them directly comparable.
4. The heatmap also revealed the correlations among the three y columns themselves.
5. All correlations were interpreted using the same if / elif / else pattern from earlier days.

## Data Quality Check

- Selected columns were checked for missing values.
- Numerical data types were confirmed before correlation analysis.
- The selected data was inspected before visualization.

## Limitations

- Only four columns were selected for this analysis.
- Correlation does not imply causation.
- Pearson correlation captures only linear relationships, not nonlinear patterns.

## Tools Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
