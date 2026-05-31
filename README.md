#  Used Car Pricing Analysis using ANOVA

![Python](https://img.shields.io/badge/Python-3.x-blue?style=flat-square&logo=python)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?style=flat-square&logo=pandas)
![SciPy](https://img.shields.io/badge/SciPy-Statistical%20Testing-8CAAE6?style=flat-square&logo=scipy)
![Seaborn](https://img.shields.io/badge/Seaborn-Visualization-4C8CBF?style=flat-square)

##  Overview

Analyzing the selling price of used cars is essential for making informed decisions in the automotive market. Using Python, this project processes and visualizes data to uncover key factors influencing car prices — aiding buyers, sellers, and enabling predictive modeling for future price estimation.

The dataset contains various attributes of used cars including price, brand, fuel type, body style, drive wheels, engine size, horsepower, and more. The goal is to analyze these factors statistically and determine their impact on the selling price using the **Analysis of Variance (ANOVA)** technique.

---

##  Dataset

The dataset (`used-car-sales-analysis.csv`) includes the following attributes:

| Feature | Description |
|---|---|
| `make` | Car brand/manufacturer |
| `fuel-type` | Fuel type (gas / diesel) |
| `body-style` | Body style (sedan, hatchback, etc.) |
| `drive-wheels` | Drive wheels (fwd, rwd, 4wd) |
| `engine-size` | Engine displacement |
| `horsepower` | Engine horsepower |
| `city-mpg` / `highway-mpg` | Fuel efficiency |
| `price` | Selling price *(target variable)* |
| + 18 more columns | — |

---

##  Tools & Libraries

| Library | Purpose |
|---|---|
| `pandas` | Data loading, cleaning, and manipulation |
| `numpy` | Numerical operations and binning |
| `matplotlib` | Base plotting and visualizations |
| `seaborn` | Statistical plots (boxplots, regression plots) |
| `scipy.stats` | ANOVA (one-way F-test) |

---

##  Project Workflow

### 1. Data Preprocessing
- Assigned descriptive column headers to the raw dataset
- Detected and removed missing/invalid values (e.g., `?` entries in the `price` column)
- Converted `city-mpg` to liters per 100 km for regional consistency
- Cast `price` column to integer type

### 2. Feature Normalisation
- Normalized `length`, `width`, and `height` columns to a 0–1 scale
- Binned `price` into three categories — **Low**, **Medium**, and **High** — using equal-width intervals
- Applied one-hot encoding to categorical variables (e.g., `fuel-type`) for model readiness

### 3. Exploratory Data Analysis (EDA)
- Boxplots for price distribution and outlier detection
- Scatter plot of `engine-size` vs `price`
- Grouped analysis by `drive-wheels` and `body-style`
- Pivot heatmap using `plt.pcolor` to visualize average price across groups
- Brand-wise price distribution using sorted boxplots

### 4. ANOVA Test
- Applied **one-way ANOVA** (`scipy.stats.f_oneway`) to test whether the mean selling price differs significantly between car brands (demonstrated with Honda vs. Subaru)
- Interpreted F-statistic and p-value to determine statistical significance

---

##  Key Visualisations

-  Boxplot — price distribution across drive-wheels
-  Scatter plot — engine size vs. price with regression line
-  Heatmap — average price by drive-wheels × body-style
-  Brand-level price comparison — sorted boxplots for all makes

---

##  Getting Started

### Prerequisites

```bash
pip install pandas numpy matplotlib seaborn scipy
```

### Run the Notebook

```bash
git clone https://github.com/LemmingTee/used-car-pricing-analysis.git
cd used-car-pricing-analysis
jupyter notebook used_car_pricing_analysis_using_anova.ipynb
```

> **Note:** Update the dataset path in the notebook to match your local file location before running.

---

##  Repository Structure

```
used-car-pricing-analysis/
│
├── used_car_pricing_analysis_using_anova.ipynb    # Main analysis notebook
├── used-car-sales-analysis.csv                    # Dataset
└── README.md                                      # Project documentation
```

---

##  Results & Insights

- **Engine size** shows a strong positive correlation with selling price
- **Drive-wheels** and **body-style** are significant factors affecting price variation
- **ANOVA test** confirms statistically significant price differences between certain car brands

---

##  Author

**Abhinav Srivastava**  
Last Updated: 31 May 2026
