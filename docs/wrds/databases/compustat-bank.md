# Compustat Bank

## Overview

Compustat Bank provides **fundamental financial data specifically for banks and financial institutions** in North America. Bank financial statements follow a different structure than non-financial companies (e.g., interest income vs. revenue, loan loss provisions, regulatory capital ratios), which is why they have a dedicated database.

**What you can find here:**

- **Bank income statement** data: interest income/expense, net interest margin, provision for loan losses, non-interest income
- **Bank balance sheet** data: total loans, deposits, securities, tier 1 capital, risk-weighted assets
- **Regulatory ratios**: capital adequacy ratios, leverage ratios
- **Annual and quarterly** financial data
- **Bank identifiers**: GVKEY, company name, ticker

## WRDS Access

- **WRDS web interface**: <a href="https://wrds-www.wharton.upenn.edu/pages/get-data/compustat-capital-iq-standard-poors/compustat/bank-daily/" target="_blank">Compustat Bank Daily</a>
- **WRDS product name**: `comp_bank_daily`
- **Python API library**: `bank`
- **Update frequency**: Daily
- **Data dictionary**: <a href="https://wrds-www.wharton.upenn.edu/data-dictionary/comp_bank_daily/" target="_blank">Link</a>

## Tables

### Core Financial Data

| Table | Description | Use case |
|-------|-------------|----------|
| `bank_funda` | **Bank Annual File** | Annual financial statements for banks — the main table for bank fundamentals |
| `bank_fundq` | **Bank Quarterly File** | Quarterly financial statements for banks |

### Identifiers & Names

| Table | Description | Use case |
|-------|-------------|----------|
| `bank_names` | **Name File** | Bank identifiers and names (annual) |
| `bank_namesq` | **Name File** | Bank identifiers and names (quarterly) |

### Detailed Item-Level Data

| Table | Description |
|-------|-------------|
| `bank_afnd1` | Bank Annual Item (A–L) |
| `bank_afnd2` | Bank Annual Item (M–Z) |
| `bank_ifndq` | Bank Interim Quarterly Item |
| `bank_ifndytd` | Bank Interim Year-to-Date Item |

### Descriptors & Metadata

| Table | Description |
|-------|-------------|
| `bank_adesind` | Bank Annual Descriptor |
| `bank_idesind` | Bank Interim Descriptor |
| `bank_aacctchg` | Bank Annual Accounting Adoption |
| `bank_iacctchg` | Bank Interim Accounting Adoption |

### Data Codes & Footnotes

| Table | Description |
|-------|-------------|
| `bank_afnddc1` | Bank Annual Data Code (A–L) |
| `bank_afnddc2` | Bank Annual Data Code (M–Z) |
| `bank_afntind` | Bank Annual Footnote |
| `bank_funda_fncd` | Bank Annual Footnote and Data Code File |
| `bank_fundq_fncd` | Bank Interim Quarterly Footnote and Data Code Items |
| `bank_ifntq` | Bank Interim Quarterly Footnote |
| `bank_ifntytd` | Bank Interim Year-to-Date Footnote |

## Example: Querying Bank Fundamentals

```python
import wrds
conn = wrds.Connection()

# List available tables
conn.list_tables(library='bank')

# Get annual bank data
bank_data = conn.raw_sql("""
    SELECT gvkey, datadate, bhck2170 AS total_assets, bhck4340 AS net_income
    FROM bank.bank_funda
    WHERE datadate >= '2019-01-01'
""", date_cols=['datadate'])
```

For more examples, see the [Python API notebook](../notebook.md).
