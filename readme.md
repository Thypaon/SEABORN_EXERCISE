# Visualization with Seaborn

This project demonstrates a variety of visualizations using the Seaborn library to explore datasets such as `mpg` (Miles Per Gallon) and `tips`. It showcases how to effectively use Seaborn’s diverse plotting tools for exploratory data analysis and presentation.

## Table of Contents

1. [Introduction](#introduction)
2. [Steps Performed](#steps-performed)
3. [Key Features of Seaborn](#key-features-of-seaborn)
4. [Installation](#installation)
5. [Usage](#usage)
6. [Example Outputs](#example-outputs)

---

### Introduction

The goal of this project is to:
- Showcase Seaborn’s functionality and themes.
- Visualize relationships, distributions, and categorical data.
- Utilize Seaborn’s built-in datasets (`mpg`, `tips`) for analysis.

### Steps Performed

1. **Setting Up Seaborn**
   - Imported necessary libraries:
     ```python
     import seaborn as sns
     import matplotlib.pyplot as plt
     ```
   - Loaded built-in datasets:
     ```python
     mpg = sns.load_dataset('mpg')
     tips = sns.load_dataset('tips')
     ```
   - Configured themes and styles:
     ```python
     sns.set_theme()
     sns.set_style('darkgrid')
     sns.set_context('paper', font_scale=1.2)
     ```

2. **Correlation and Heatmap**
   - Calculated correlation matrix for numeric columns:
     ```python
     mpg.corr(numeric_only=True)
     ```
   - Visualized with a heatmap:
     ```python
     sns.heatmap(mpg.corr(numeric_only=True))
     ```

3. **Scatter Plots and Line Plots**
   - Scatterplot of `weight` vs. `mpg`, colored by `origin`:
     ```python
     sns.scatterplot(data=mpg, x='weight', y='mpg', hue='origin')
     ```
   - Lineplot and pointplot for `model_year` vs. `mpg`:
     ```python
     sns.lineplot(data=mpg, x='model_year', y='mpg', hue='origin')
     sns.pointplot(data=mpg, x='model_year', y='mpg', hue='origin')
     ```

4. **Distribution Plots**
   - Histograms and KDE plots for `mpg`:
     ```python
     sns.histplot(data=mpg, x='mpg', kde=True, bins=10)
     sns.kdeplot(data=mpg, x='model_year', y='mpg', hue='origin')
     ```
   - ECDF and Rug plots:
     ```python
     sns.ecdfplot(data=mpg, x='mpg')
     sns.rugplot(data=mpg, x='mpg')
     ```

5. **Categorical Plots**
   - Bar plots, box plots, and violin plots:
     ```python
     sns.barplot(data=mpg, x='origin', y='mpg', hue='origin')
     sns.boxplot(data=mpg, x='origin', y='mpg', hue='origin')
     sns.violinplot(data=mpg, x='origin', y='mpg', hue='origin')
     ```

6. **Joint and Pair Plots**
   - Joint plots for `weight` and `mpg` with various styles:
     ```python
     sns.jointplot(data=mpg, x='weight', y='mpg', kind='reg')
     sns.jointplot(data=mpg, x='weight', y='mpg', kind='hex')
     ```
   - Pair plot for relationships across multiple variables:
     ```python
     sns.pairplot(data=mpg, hue='origin')
     ```

7. **Facet Grids**
   - Visualized `tips` dataset with FacetGrid:
     ```python
     f6 = sns.FacetGrid(tips, col='day', row='sex')
     f6.map_dataframe(sns.scatterplot, x='tip', y='total_bill')
     ```

### Key Features of Seaborn

- **Themes and Styles**: Easily apply themes like `darkgrid` and adjust context for publication-ready plots.
- **Built-in Datasets**: Use preloaded datasets like `mpg` and `tips` to quickly experiment.
- **Comprehensive Plot Types**: From simple scatterplots to complex facet grids, Seaborn simplifies visualization tasks.

### Installation

Ensure the following libraries are installed:

```bash
pip install seaborn matplotlib
```

### Usage

1. Import Seaborn and other dependencies.
2. Load a dataset, configure themes, and start visualizing:

```python
sns.set_theme()
data = sns.load_dataset('mpg')
sns.scatterplot(data=data, x='weight', y='mpg', hue='origin')
plt.show()
```

### Example Outputs

- Heatmaps, histograms, and scatterplots show data distributions and relationships.
- FacetGrid allows multi-dimensional visualizations, enabling comparisons across subsets of data.