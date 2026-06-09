# Data Visualization with Python and MySQL

## Description

This project integrates Python with Pandas, Matplotlib, and Seaborn to explore and visualize data from the `world_transactions` database (Sprint 4). It covers the full pipeline from MySQL connection to advanced visualizations.

## Database

**Source:** MySQL — `world_transactions`  
**Tables used:** `card_status`, `company`, `credit_card`, `products`, `transactions`, `transactions_products`, `users`

## File

| File | Description |
|------|-------------|
| `visualizaciones.ipynb` | Main notebook with all visualizations and interpretations |

## Libraries

- `pandas` — data manipulation and merges
- `matplotlib` — base plotting
- `seaborn` — statistical visualizations
- `sqlalchemy` — MySQL connection
- `mysql-connector-python` — MySQL driver

## Connection

The notebook connects to MySQL using SQLAlchemy. Password is handled securely via `getpass` — it is never stored in the code or the notebook.

```python
from sqlalchemy import create_engine
import getpass

password = getpass.getpass("Introduce tu contraseña: ")
engine = create_engine(f"mysql+mysqlconnector://root:{password}@localhost/world_transactions")
```

## Level 1 — Visualizations

| Type | Variables | Tables | Chart |
|------|-----------|--------|-------|
| 1 numeric variable | `amount` | transactions | Histogram |
| 2 numeric variables | `price`, `weight` | products | Scatter plot |
| 1 categorical variable | `country` | company | Bar chart |
| 1 categorical + 1 numeric | `country`, `amount` | users + transactions | Boxplot |
| 2 categorical variables | `country`, `estado_tarjeta` | users + transactions + card_status | Grouped bar chart |
| 3 combined variables | `country_usuario`, `country_compania`, transactions count | users + transactions + company | Heatmap |
| Pairplot | `amount`, `price`, `weight` | transactions + products | Pairplot |

## Level 2 — Correlation Analysis

| Exercise | Variables | Chart |
|----------|-----------|-------|
| Correlation matrix | `amount`, `price`, `weight` | Correlation heatmap |
| Jointplot | `amount`, `price` | Jointplot |

## Key Findings

- The distribution of transaction amounts is right-skewed, with most transactions between 100 and 350.
- No correlation exists between product weight and price — product pricing is independent of weight.
- Transaction amounts are homogeneous across all countries, with a median of approximately 250.
- The vast majority of transactions are made with active cards across all countries.
- A geographic segmentation pattern is visible: European users transact with European companies, while Canada and the US transact within their own region.
- `amount` and `price` show a perfect correlation (1.00), confirming that transaction amount directly reflects product price.
