# WRDS Bond Returns

## Overview

WRDS Bond Returns provides **monthly corporate bond return data**, constructed by WRDS from TRACE transaction data. This dataset makes it straightforward to use bond returns in academic research without having to compute them from raw TRACE trades yourself.

**What you can find here:**

- **Monthly bond returns**: total return, price return, accrued interest return
- **Bond characteristics**: coupon, maturity, rating, offering amount
- **Bond pricing**: end-of-month prices, yields
- **Coverage**: US corporate bonds

## WRDS Access

- **WRDS web interface**: <a href="https://wrds-www.wharton.upenn.edu/pages/get-data/wrds-bond-returns/wrds-bond-returns/" target="_blank">WRDS Bond Returns</a>
- **Python API library**: `wrdsapps_bondret`
- **Data dictionary**: <a href="https://wrds-www.wharton.upenn.edu/data-dictionary/wrdsapps_bondret/" target="_blank">Link</a>

## Example: Querying Bond Returns

```python
import wrds
conn = wrds.Connection()

# List available tables
conn.list_tables(library='wrdsapps_bondret')

# Get monthly bond returns
returns = conn.raw_sql("""
    SELECT cusip, date, bond_ret, t_volume, price_eom, rating
    FROM wrdsapps_bondret.wrds_bond_returns
    WHERE date >= '2023-01-01'
    LIMIT 100
""", date_cols=['date'])
```

For more examples, see the [Python API notebook](../notebook.md).
