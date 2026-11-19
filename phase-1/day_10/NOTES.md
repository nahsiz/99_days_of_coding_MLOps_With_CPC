# Day 10 — Multi-Column Correlation Analysis

## What I Built

- Loaded the House Price dataset using Pandas.
- Selected two feature columns (area_sqft, distance_km) and one target column (price).
- Calculated two Pearson correlation coefficients against the same target column.
- Created a correlation heatmap for the three selected columns.
- Created two scatter plots with regression lines, both sharing the same y-axis (price).
- Generated individual histograms for all three selected columns.
- Used two joint plots to visualize each feature-target relationship with distributions.
- Interpreted both correlation coefficients to identify the direction of each linear relationship.

## What I Learned

- How to calculate multiple correlations against a single fixed target column.
- How to build a 3×3 correlation heatmap instead of a 2×2 one.
- How to keep one axis fixed so two relationships can be compared directly.
- How to interpret positive and negative relationships for two different features.
- How to visualize two different feature-target pairs together.
- How to read feature-to-feature correlation inside the same heatmap.

## Key Findings

1. The analysis used price as the shared target column for both comparisons.
2. Two Pearson correlation coefficients were computed: area_sqft vs price and distance_km vs price.
3. Both regression plots share the same y-axis (price), so they can be compared directly.
4. The heatmap also revealed the correlation between the two features themselves.
5. Both correlations were interpreted using the same if / elif / else pattern from Day 9.

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
