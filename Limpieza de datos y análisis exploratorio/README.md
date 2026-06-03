# Data Cleaning & Exploratory Analysis
 
**Tools:** Python · pandas · NumPy · matplotlib · seaborn · openpyxl
 
---
 
## Overview
 
End-to-end data wrangling and analysis pipeline built on an employee survey dataset. The project covers data normalization, feature engineering, salary aggregation, and automated chart generation — plus a combinatorial routing problem solved with a greedy nearest-neighbor algorithm.
 
---
 
## Project Structure
 
```
sprint10/
├── encuestas.ipynb              # Main notebook (all levels)
├── Encuesta_trabajadores.xlsx   # Source dataset
├── matriu_distancies.xlsx       # City distance matrix
├── datos_Grup_A.csv             # Exported subsets by professional group
├── datos_Grup_B.csv
├── datos_Grup_C.csv
├── datos_Grup_D.csv
├── resum_grups.csv              # Summary: headcount, avg salary, median age by group
└── graf_*.png                   # Auto-generated charts (Level 3)
```
 
---
 
## What's Inside
 
### Level 1 — Data Cleaning & Normalization
- Imported and sorted the survey dataset without modifying the source file
- Engineered new columns: full name, Spain-born flag, datetime birthdate, and current age
- Standardized gender codes (`H → Male, D → Female, A → Other, NC → NaN`)
- Set DNI as the DataFrame index; verified uniqueness
- Built salary summary tables by gender (mean, median, min, max) and a pivot table by gender × country of origin with conditional formatting
### Level 2 — Salary Updates & Exports
- Merged salary increment percentages by professional group (`Grup A–D`) and applied them programmatically — no hardcoded values
- Exported one `.csv` per professional group
- Generated a summary file with headcount, average salary, and median age per group
### Level 3 — Generalized Charting & Route Optimization
- **Auto-chart function:** detects column dtype and generates the appropriate chart type (histogram/boxplot for numeric, bar chart for categorical, bar chart by year for datetime); validated on the seaborn `penguins` dataset
- **Travelling Salesman (greedy):** loads a city distance matrix, removes non-driveable cities (Las Palmas, Palma), and returns the shortest route found via nearest-neighbor heuristic from any starting city — including total distance and the optimal starting point across all cities
---
 
## Key Decisions
 
- Salary increments stored as strings (`"3,5%"`) — converted to floats programmatically using `str.replace` and `pd.to_numeric` before applying
- Age calculation uses `datetime.today()` to remain accurate on any run date
- The routing algorithm is intentionally greedy (not optimal); complexity vs. interpretability trade-off documented in the notebook

Salary increments stored as strings ("3,5%") — converted to floats programmatically using str.replace and pd.to_numeric before applying
Age calculation uses datetime.today() to remain accurate on any run date
