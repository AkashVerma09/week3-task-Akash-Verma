# Week 3 – EDA on a Real-World-Like Dataset (Akash Verma)

## Objective
Practice **data cleaning**, **visualization**, and **exploratory data analysis (EDA)** on a messy CSV dataset to learn how to prepare data for insights.

## Dataset
A custom **Student Performance** CSV with:
- Numerical columns: `Age`, `StudyHours`, `MathScore`, `ReadingScore`, `WritingScore`, `AttendanceRate`
- Categorical columns: `Gender`, `City`, `Class`, `Passed`, plus `Name`
- Deliberate **missing values**, inconsistent categories (e.g., `'male'`, `'M'`, `' Female'`), and **duplicates**

Files:
- `data/students_raw.csv` – original messy dataset
- `data/students_clean.csv` – cleaned dataset (created by the notebook or CLI)

## What’s Included
- **Jupyter Notebook**: `EDA_Student_Performance.ipynb` – step-by-step loading, cleaning, EDA, and plots
- **CLI Script**: `eda.py` – console menu to perform key EDA/cleaning actions and generate plots
- **Plots** (sample screenshots):
  - `plots/hist_age.png`
  - `plots/bar_gender.png`
  - `plots/scatter_study_vs_avg.png`

## How to Run
### Notebook
1. Create and activate a virtual environment (optional but recommended).
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Launch Jupyter:
   ```bash
   jupyter notebook
   ```
4. Open `EDA_Student_Performance.ipynb` and run cells top-to-bottom.

Menu options include:
- Basic info (head, dtypes, missing counts)
- Standardize categorical values (Gender/City/Passed)
- Fill missing values
- Remove duplicates
- Derive features (`AverageScore`, fix `Passed`)
- Summary stats, categorical modes
- NumPy variance & correlation
- Visualizations (hist, bar, scatter) – saved in `plots/`
- Save cleaned dataset to `outputs/students_cleaned.csv`

## Approach
1. **Load** raw CSV with obvious data quality issues.
2. **Clean**:
   - Strip whitespace, title-case and map categories (`M/male/MALE` → `Male`, `Bangalore` → `Bengaluru`)
   - Remove duplicates
   - Impute missing values (median for numeric, mode for categorical)
   - Derive `AverageScore` and ensure `Passed` is consistent
3. **Explore**:
   - Summary stats for numeric columns
   - Top values for categorical columns
   - NumPy variance and correlation matrix
4. **Visualize**:
   - Histogram of `Age`
   - Bar chart of `Gender`
   - Scatter of `StudyHours` vs `AverageScore`

## Challenges
- Designing realistic **inconsistencies** and **missingness** to simulate real-world data
- Ensuring robust imputations without leakage
- Keeping visualizations and menu-driven flow simple and reliable
