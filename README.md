# Retail Customer Segmentation with K-Means

An unsupervised machine-learning project that groups retail customers using demographic and purchasing-behaviour variables.

## Project objective

Customer segmentation can help a retailer explore groups with different income, age and spending patterns. This notebook combines exploratory data analysis, the elbow method, K-means clustering and two- and three-dimensional visualisation.

## Dataset

The included `Mall_Customers.csv` file contains **200 customers** and five columns:

| Column | Description |
|---|---|
| `CustomerID` | Customer identifier |
| `Gender` | Recorded gender |
| `Age` | Customer age |
| `Annual Income (k$)` | Annual income in thousands |
| `Spending Score (1-100)` | Store-assigned spending score |

The saved notebook checks show no missing values in these columns.

## Analysis workflow

1. Inspect dimensions, types, descriptive statistics and missing values.
2. Explore age, income and spending-score distributions.
3. Compare variables through scatter, regression, violin and swarm plots.
4. Calculate within-cluster sum of squares across candidate values of *k*.
5. Select cluster counts using elbow plots.
6. Visualise cluster assignments and centroids.

## Clustering experiments

| Feature space | Selected clusters |
|---|---:|
| Age + spending score | 4 |
| Annual income + spending score | 5 |
| Age + annual income + spending score | 6 |

The primary business-facing segmentation uses annual income and spending score with **five clusters**. A three-dimensional Plotly view explores the combined age, income and spending-score solution.

## Repository contents

- `TASK02.ipynb` — exploratory analysis and clustering workflow
- `Mall_Customers.csv` — input dataset

## Run locally

```bash
git clone https://github.com/Tejasvi-Ponugoti/PRODIGY_ML_02.git
cd PRODIGY_ML_02
python -m venv .venv
pip install pandas numpy matplotlib seaborn plotly scikit-learn jupyter
jupyter notebook TASK02.ipynb
```

The current notebook contains a Windows-specific dataset path. Replace it with:

```python
df = pd.read_csv("Mall_Customers.csv")
```

## Interpretation and limitations

The clusters are exploratory segments, not verified customer personas. Cluster numbers are arbitrary and should be translated into business labels only after reviewing their centroids and validating them with stakeholders.

Further improvements include:

- Standardising features before clustering
- Comparing silhouette scores across candidate cluster counts
- Testing cluster stability
- Profiling each segment with interpretable business labels
- Separating model development from visualisation code

## Skills demonstrated

Python · Pandas · Exploratory data analysis · K-means · Unsupervised learning · Matplotlib · Seaborn · Plotly
