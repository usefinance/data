# Mergent Fixed Income Securities Database (FISD)

## Overview

The Mergent FISD provides **comprehensive data on fixed income (bond) securities** issued in the United States. It covers corporate bonds, agency bonds, and US government bonds.

**What you can find here:**

- **Bond issue details**: issue date, maturity, coupon rate, coupon type (fixed/floating/zero), offering amount, currency
- **Issuer information**: issuer name, industry, SIC code, country, state
- **Bond characteristics**: callable, convertible, puttable, sinking fund provisions, covenants
- **Credit ratings**: Moody's and S&P ratings at issuance and over time
- **Transactions by insurance companies**: NAIC insurance company bond holdings and transactions

## WRDS Access

- **WRDS web interface**: <a href="https://wrds-www.wharton.upenn.edu/pages/get-data/lseg-mergent/" target="_blank">LSEG / Mergent</a>
- **WRDS product name**: `fisd` (or search for Mergent in the WRDS web interface)
- **Python API library**: `fisd`
- **Update frequency**: Varies by table
- **Data dictionary**: <a href="https://wrds-www.wharton.upenn.edu/data-dictionary/fisd/" target="_blank">Link</a>

## Key Tables

Use `conn.list_tables(library='fisd')` in the Python API to see the full list. Key tables typically include:

| Table | Description | Use case |
|-------|-------------|----------|
| `fisd_mergedissue` | Bond Issues | Master file of bond issues with all characteristics |
| `fisd_mergedissuer` | Bond Issuers | Issuer-level information |

## Example: Querying Bond Data

```python
import wrds
conn = wrds.Connection()

# List available tables
conn.list_tables(library='fisd')

# Get corporate bond issues
bonds = conn.raw_sql("""
    SELECT complete_cusip, issue_name, maturity, offering_amt,
           coupon, coupon_type, offering_date
    FROM fisd.fisd_mergedissue
    WHERE security_level = 'SEN'
      AND offering_date >= '2020-01-01'
    LIMIT 100
""", date_cols=['maturity', 'offering_date'])
```

For more examples, see the [Python API notebook](../notebook.md).
