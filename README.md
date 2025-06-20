Project: Carbon Emission Prediction
# CO₂ Emissions Data Cleaning

This project involves cleaning and preparing country-specific CO₂ emissions and related data for further analysis and modeling.

## 📁 Dataset Description

The original dataset contains:
- Country information
- Various indicators over multiple years (1990–2011)
- Wide-format year columns (e.g., '1990', '1991', ...)

## 🧹 Data Cleaning Steps

1. **Loaded the raw data** into a Pandas DataFrame.
2. **Transformed the dataset from wide to long format** using `pd.melt()`, converting year columns into a single 'year' column.
3. **Checked and counted missing values**:
   - By year
   - By country
   - By column
4. **Filtered**:
   - Years between 1991 and 2008 (to reduce missing values)
   - Countries with **no missing values** (or optionally minimal missing values)
5. **Exported** the cleaned dataset to:
   - `cleaned_data.csv`

## 🗃️ Output

- `cleaned_data.csv`: Long-format cleaned dataset ready for analysis or modeling.

## 🔧 Dependencies

- Python 3.7+
- Pandas
- (Optional) openpyxl – if exporting to Excel

Install dependencies:
```bash
pip install pandas openpyxl
