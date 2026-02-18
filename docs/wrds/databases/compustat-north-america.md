# Compustat North America

## Overview

Compustat North America provides **fundamental financial data for publicly traded companies in the United States and Canada**. It is one of the most widely used databases in academic finance and accounting research.

**What you can find here:**

- **Income statement** data: revenue, cost of goods sold, operating income, net income, EPS, etc.
- **Balance sheet** data: total assets, liabilities, equity, cash, debt, inventories, etc.
- **Cash flow statement** data: operating, investing, and financing cash flows
- **Stock price and return** data: daily/monthly prices, shares outstanding, market capitalization
- **Company identifiers**: GVKEY (Compustat's own key), CUSIP, CIK, ticker, company name, SIC/NAICS codes
- **Segment data**: geographic and business segment breakdowns (see [Compustat Historical Segments](compustat-segments.md))

## WRDS Access

- **WRDS web interface**: <a href="https://wrds-www.wharton.upenn.edu/pages/get-data/compustat-capital-iq-standard-poors/compustat/north-america-daily/" target="_blank">Compustat North America Daily</a>
- **WRDS product name**: `comp_na_daily_all`
- **Python API library**: `comp`
- **Update frequency**: Daily
- **Data dictionary**: <a href="https://wrds-www.wharton.upenn.edu/data-dictionary/comp_na_daily_all/" target="_blank">Link</a>

## Key Tables

The tables below are the most commonly used. Use `conn.list_tables(library='comp')` in the Python API to see the full list.

### Company Fundamentals

| Table | Description | Use case |
|-------|-------------|----------|
| `funda` | **Fundamental Annual** | Annual financial statements (income statement, balance sheet, cash flow). This is the most commonly used Compustat table. |
| `fundq` | **Fundamental Quarterly** | Quarterly financial statements |
| `company` | **Company** | Company identifiers and descriptors (name, ticker, GVKEY, SIC code, state, etc.) |

### Security (Stock) Data

| Table | Description | Use case |
|-------|-------------|----------|
| `secd` | **Security Daily** | Daily stock prices, returns, volume, shares outstanding |
| `secm` | **Security Monthly** | Monthly stock prices and shares outstanding |

### Identifiers & Names

| Table | Description | Use case |
|-------|-------------|----------|
| `names` | **Name File** | Historical company names and identifiers |
| `security` | **Security** | Security-level identifiers (CUSIP, ticker, exchange) |

## Example: Querying Annual Fundamentals

```python
import wrds
conn = wrds.Connection()

# Get Apple's annual financial data from 2019 onwards
apple = conn.raw_sql("""
    SELECT gvkey, datadate, fyear, at, sale, ni
    FROM comp.funda
    WHERE gvkey = '16917'
      AND datadate >= '2019-01-01'
      AND datafmt = 'STD'
      AND consol = 'C'
      AND indfmt = 'INDL'
""", date_cols=['datadate'])
```

> **Tip**: Always filter on `datafmt = 'STD'`, `consol = 'C'`, and `indfmt = 'INDL'` when querying `funda`/`fundq` to avoid duplicate rows (restated data, different consolidation levels, etc.).

For more examples, see the [Python API notebook](../notebook.md).
