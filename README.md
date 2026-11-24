# ABC Company – Employee Data Analysis

Python project (pandas, NumPy, Matplotlib, Seaborn, SciPy) analysing an employee dataset of **458 rows × 9 columns**
(`Name, Team, Number, Position, Age, Height, Weight, College, Salary`).

## Repository contents
| File | Description |
|---|---|
| `ABC_Company_Analysis.ipynb` | Full notebook: preprocessing, analysis, charts, data story |
| `ABC Company.xlsx` | The dataset (**add this file before you push**) |
| `images/` | Charts exported by the notebook |
| `README.md` | This overview |

## How to run
```bash
pip install pandas numpy matplotlib seaborn scipy openpyxl jupyter
jupyter notebook ABC_Company_Analysis.ipynb
```
Keep `ABC Company.xlsx` in the same folder as the notebook, then use *Run All*.

## 1. Preprocessing
- **Height** – the original values were corrupted (Excel converted entries like `6-2` into dates such as `06-Feb`). As instructed, the column was replaced with random integers between **150 and 180** (fixed seed `42`, so it's reproducible).
- **Salary** – converted to numeric; missing values filled with the **median** salary (salary is right-skewed, so the median is more robust than the mean).
- Column names and text fields were stripped of stray whitespace; duplicate rows and missing ages were checked.

## 2. Analysis tasks and visualisations
| # | Task | Method | Chart(s) |
|---|---|---|---|
| 1 | Employees per team + % split | `value_counts()` and percentage of total | Horizontal bar + pie |
| 2 | Employees by position | Counts, share, roster per position, team × position table | Bar + pie + heatmap |
| 3 | Predominant age group | Age binned into Under 25 / 25-29 / 30-34 / 35-39 / 40+ | Bar (winner highlighted) + histogram |
| 4 | Highest salary expenditure (team & position) | `groupby().sum()` on Salary | Bar charts + team × position heatmap |
| 5 | Age vs salary correlation | Pearson & Spearman coefficients | Scatter with regression line + average salary by age + correlation matrix |

## 3. Key findings
> **Fill this section in after running the notebook** – the last cell of the notebook prints the data story with your exact numbers. Copy it here. It covers:
> - team with the most employees and its % share
> - most / least common position
> - predominant age group
> - team and position with the highest salary spend
> - strength and direction of the age–salary correlation

## 4. Notes
- Height is synthetic after cleaning, so it is not used in any insight.
- Charts are saved to `images/` every time the notebook runs.
