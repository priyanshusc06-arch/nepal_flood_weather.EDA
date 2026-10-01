# Nepal Flood Weather Dataset — Exploratory Data Analysis (EDA)

This project performs a complete, step-by-step Exploratory Data Analysis (EDA) on the dataset:

**`nepal_flood_weather_dataset_kaggle_2023_2026.csv`**

The objective is to understand the dataset structure, data quality, distributions, missing values, outliers, correlations, time-based patterns, and flood-related insights using Python.

---

## 📌 Project Overview

This EDA project analyzes Nepal flood and weather-related data from 2023 to 2026. It focuses on:

- Understanding the dataset structure
- Identifying missing and duplicate data
- Analyzing numerical and categorical variables
- Detecting outliers
- Exploring correlations between weather variables
- Performing time-series analysis where possible
- Identifying flood-related patterns and risk factors
- Saving cleaned data and visualizations

The analysis is designed to be error-safe and works even if some expected columns are not present in the dataset.

---

## 📁 Dataset

| Item | Details |
|---|---|
| File name | `nepal_flood_weather_dataset_kaggle_2023_2026.csv` |
| File format | CSV |
| Time range | 2023–2026 |
| Domain | Weather, rainfall, flood, and disaster analysis |
| Main use case | Exploratory Data Analysis and flood-risk understanding |

Place the dataset in the same folder as the Python notebook or script.

---

## 🛠️ Technologies Used

- Python 3
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Jupyter Notebook / Google Colab / VS Code

Optional:

- Plotly, for interactive visualizations

---

## ⚙️ Installation

Install the required Python libraries:

```bash
pip install pandas numpy matplotlib seaborn
```

If you want to use interactive charts:

```bash
pip install plotly
```

---

## 🚀 How to Run

### Option 1: Jupyter Notebook

1. Open the notebook in Jupyter Notebook, JupyterLab, or VS Code.
2. Keep the CSV file in the same folder.
3. Run the cells one by one.
4. Check the generated outputs and charts.

### Option 2: Google Colab

1. Upload the CSV file using:

```python
from google.colab import files
uploaded = files.upload()
```

2. Run the EDA code cells.
3. Download the cleaned dataset and generated plots after analysis.

---

## 🧭 EDA Steps

### 1. Import Libraries and Load Dataset

- Import required Python libraries.
- Load the CSV file safely.
- Check whether the file exists.
- Display the first few rows.
- Print the number of rows and columns.

### 2. Basic Dataset Inspection

- Display dataset shape.
- Display column names and data types.
- Use `df.info()` to understand data structure.
- Use `df.describe()` for numerical summary statistics.
- Check the number of unique values in each column.

### 3. Missing Value Analysis

- Calculate missing values for every column.
- Calculate missing-value percentage.
- Visualize missing values using a bar chart.
- Decide whether imputation is required.

### 4. Duplicate Value Analysis

- Identify duplicate rows.
- Remove duplicates from a cleaned copy.
- Compare dataset size before and after cleaning.

### 5. Column Type Detection

- Automatically detect:
  - Numerical columns
  - Categorical columns
  - Datetime columns
- Identify possible flood-related columns using keywords such as:
  - `flood`
  - `rainfall`
  - `rain`
  - `water`
  - `river`
  - `level`
  - `disaster`
  - `risk`
  - `severity`
  - `damage`
  - `warning`

### 6. Data Cleaning

- Remove unnecessary spaces from text columns.
- Convert valid date columns to datetime format.
- Handle invalid dates using `errors="coerce"`.
- Check infinite values in numerical columns.
- Impute missing values:
  - Median for numerical columns
  - Mode for categorical columns

No rows or columns are deleted blindly.

### 7. Univariate Analysis — Numerical Columns

- Histograms with KDE
- Boxplots
- Skewness analysis
- Outlier detection

### 8. Univariate Analysis — Categorical Columns

- Value counts
- Countplots
- Category imbalance analysis

### 9. Outlier Detection

- Uses the Interquartile Range (IQR) method.
- Calculates outlier count and percentage.
- Boxplots are generated for visual inspection.
- Outliers are not automatically removed because extreme weather values may be genuine flood events.

The IQR formula is:

\[
IQR = Q3 - Q1
\]

Values outside the following range are considered potential outliers:

\[
[Q1 - 1.5 \times IQR,\ Q3 + 1.5 \times IQR]
\]

### 10. Correlation Analysis

- Calculates correlations between numerical variables.
- Generates an annotated heatmap.
- Identifies strong positive and negative relationships.

### 11. Bivariate Analysis

- Scatterplots for important numerical variable pairs.
- Boxplots or violin plots for categorical comparisons.
- Compares weather-related variables across flood-related categories, if available.

### 12. Time-Series Analysis

- If a datetime column exists, data is sorted by date.
- Monthly resampling is performed where appropriate.
- Trends and seasonal patterns are visualized.
- If no valid date column exists, the code prints a clear message instead of failing.

### 13. Flood-Specific Analysis

- Searches for flood-related columns.
- Displays target class distribution, if available.
- Compares numerical features across flood classes.
- Checks for class imbalance.

### 14. Key Insights

The final section summarizes:

- Data-quality issues
- Missing-value patterns
- Important distributions
- Outliers
- Correlation findings
- Seasonal or time-based patterns
- Flood-related insights

### 15. Save Outputs

The project saves:

- Cleaned dataset: `cleaned_nepal_flood_weather_dataset.csv`
- All visualizations in the `eda_plots` folder

---

## 📊 Expected Outputs

After running the project, you should get:

- Data-quality report
- Missing-value chart
- Distribution plots
- Boxplots
- Correlation heatmap
- Time-series plots
- Flood-related visualizations
- Cleaned CSV file
- Folder containing all EDA charts

Example output folder structure:

```text
project-folder/
│
├── nepal_flood_weather_dataset_kaggle_2023_2026.csv
├── eda_notebook.ipynb
├── cleaned_nepal_flood_weather_dataset.csv
└── eda_plots/
    ├── missing_values.png
    ├── numerical_distributions.png
    ├── boxplots.png
    ├── correlation_heatmap.png
    ├── time_series_trends.png
    └── flood_related_analysis.png
```

---

## ✅ Error-Safety Features

This project includes safeguards to avoid common EDA errors:

- Checks whether the CSV file exists before loading it.
- Does not assume fixed column names.
- Checks column existence before plotting.
- Handles missing datetime values safely.
- Avoids plotting empty data.
- Handles categorical columns with too many unique values carefully.
- Uses current, non-deprecated pandas and seaborn syntax.
- Prevents `KeyError`, `FileNotFoundError`, `TypeError`, and common plotting errors.

---

## 📈 Possible Insights

Depending on the available columns, this analysis can help identify:

- Months or seasons with higher rainfall
- Relationship between rainfall and flood-related indicators
- Extreme weather events and outliers
- Missing or inconsistent records
- Variables most strongly related to flood risk
- Time-based trends between 2023 and 2026
- Potential data-quality issues in the dataset

---

## 📌 Important Note

EDA is an exploratory step. It does not prove causation. For example, even if rainfall shows a strong correlation with a flood-related variable, further statistical modeling and domain validation are required before drawing final conclusions.

---

## 👤 Author

Prepared as part of a data analytics / data science EDA project.

---

## 📄 License

This project is for educational and analytical purposes. Please check the original Kaggle dataset license before redistribution or commercial use.
