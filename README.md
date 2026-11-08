# English Premier League 2020–21: Exploratory Data Analysis

A Python notebook exploring player statistics from the 2020–21 English Premier League season. The project demonstrates data inspection, filtering, derived metrics, grouped summaries, rankings, and visualization with pandas, NumPy, Matplotlib, and Seaborn.

[View the analysis notebook](eda_on_football_data.ipynb)

## Dataset

The bundled [EPL_20_21.csv](Data/EPL_20_21.csv) contains **532 player records and 18 columns**, with no missing values in the supplied file. Fields include club, nationality, position, age, appearances, minutes, goals, assists, passing statistics, penalties, and cards.

The repository does not document the original dataset source or its license. These details should be confirmed before redistributing or reusing the data elsewhere. Counts and totals below describe the supplied dataset, rather than an independently verified official league record.

## Analysis workflow

- Inspect data types, descriptive statistics, and missing values.
- Derive minutes per appearance and goals per appearance.
- Summarize goals, penalty attempts, and penalty conversion.
- Explore nationality, club representation, and age distributions.
- Compare club goal and assist totals and rank players by goals, assists, goals per appearance, and yellow cards.
- Present comparisons using bar charts, pie charts, and box plots.

## Selected findings

Checked against the bundled CSV:

| Measure | Result |
| --- | ---: |
| Sum of player goals | 986 |
| Sum of player assists | 685 |
| Penalties scored / attempted | 102 / 125 (81.6%) |
| Distinct nationality codes | 59 |
| Highest goals total | Harry Kane — 23 |
| Highest assists total | Harry Kane — 14 |

## Run locally

Use Python 3 with the packages listed in `requirements.txt`. The original notebook records Python 3.10.4; dependency versions are not locked to that historical environment.

```bash
git clone https://github.com/ishtiakrongon/PythonProject2-Exploratory_Data_Analysis_Using_Python.git
cd PythonProject2-Exploratory_Data_Analysis_Using_Python
python -m venv .venv
```

Activate the environment:

```powershell
# Windows PowerShell
.venv\Scripts\Activate.ps1
```

```bash
# macOS / Linux
source .venv/bin/activate
```

Install dependencies and start Jupyter **from the repository root**:

```bash
python -m pip install -r requirements.txt
python -m notebook
```

Open `eda_on_football_data.ipynb`, select the environment's Python kernel, and run all cells from top to bottom. The notebook loads `Data/EPL_20_21.csv` using a relative path; no personal drive path or separate dataset download is required. GitHub also displays the saved notebook outputs without installation.

## Repository contents

```text
Data/EPL_20_21.csv           Input dataset
eda_on_football_data.ipynb  Analysis and saved visualizations
requirements.txt           Runtime and notebook dependencies
README.md                  Project overview and setup
```

## Interpretation and limitations

- This is descriptive exploration of one season, not a predictive model or a causal study.
- Missing values are checked; the supplied data has none. The notebook does not demonstrate missing-value imputation.
- Club player counts represent records in this dataset, not necessarily registered squad sizes.
- `MinsPerMatch` truncates to whole minutes; `GoalsPerMatch` uses appearances, not 90-minute equivalents, and has no minimum-appearance threshold.
- The age-distribution chart includes players aged 20 in its youngest group; the separate under-20 club analysis uses ages strictly below 20.
- The forward filter selects the exact `FW` label, excluding combined position labels.
- Club goal totals sum player goals. The assisted-goals chart infers unassisted goals by subtracting total assists from player goals; it does not use event-level goal records.
- Calculations, rankings, and saved chart outputs are retained from the original analysis. New library versions may change chart appearance or emit deprecation warnings.
