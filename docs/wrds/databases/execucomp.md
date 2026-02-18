# ExecuComp

## Overview

ExecuComp provides **detailed executive and director compensation data for S&P 1500 companies** (S&P 500, S&P MidCap 400, and S&P SmallCap 600). The data is sourced from companies' annual proxy statements (DEF 14A filings).

**What you can find here:**

- **Executive compensation**: salary, bonus, stock awards, option awards, non-equity incentive plan, pension changes, total compensation (TDC1/TDC2)
- **Stock option details**: grants, exercises, Black-Scholes valuations, outstanding awards
- **Director compensation**: board member fees, stock awards, option awards
- **Pension and deferred compensation**: present value of pension benefits, deferred compensation balances
- **Company-level data**: CEO pay ratio, company financial metrics linked to compensation
- **Executive information**: name, title, age, tenure, gender

Coverage starts from **1992** for most companies.

## WRDS Access

- **WRDS web interface**: <a href="https://wrds-www.wharton.upenn.edu/pages/get-data/compustat-capital-iq-standard-poors/compustat/execucomp/" target="_blank">ExecuComp</a>
- **WRDS product name**: `comp_execucomp`
- **Python API library**: `comp_execucomp`
- **Update frequency**: Monthly
- **Data dictionary**: <a href="https://wrds-www.wharton.upenn.edu/data-dictionary/comp_execucomp/" target="_blank">Link</a>

## Tables

### Core Compensation Data

| Table | Description | Use case |
|-------|-------------|----------|
| `anncomp` | **Annual Compensation** | Merged aggregate-level data — the main table for executive compensation. Contains salary, bonus, stock/option awards, total compensation per executive per year. |
| `directorcomp` | **Director Compensation** | Board member compensation data |
| `deferredcomp` | **Deferred Compensation** | Deferred compensation plan details |
| `pension` | **Pension Benefits** | Present value of accumulated pension benefits |

### Award & Grant Details

| Table | Description | Use case |
|-------|-------------|----------|
| `outstandingawards` | **Outstanding Equity Awards** | Unvested stock and unexercised option awards at fiscal year end |
| `planbasedawards` | **Plan Based Awards** | Equity and non-equity incentive plan awards granted during the year |
| `ex_black` | Black-Scholes Means | Black-Scholes valuations of option grants |
| `ltawdtab` | Long Term Incentive Awards (1992 format) | Historical LTI award data in legacy format |
| `stgrttab` | Stock Option Grants (1992 format) | Historical option grant data in legacy format |

### Company & Executive Identifiers

| Table | Description | Use case |
|-------|-------------|----------|
| `exnames` | **Company Names** | Company names and identifiers (GVKEY, ticker, CUSIP) |
| `person` | **Executive Information** | Executive biographical data (name, gender, age) |
| `colev` | **Company Level Information** | Company-level aggregates and financial data |
| `coperol` | **Company-Person Specifics** | Mapping of executives to companies and roles |
| `ex_header` | Combined Header | Combined header with company and person info |

### Legacy / Historical

| Table | Description |
|-------|-------------|
| `codirfin` | Company Financial and Director Compensation (2005 and prior) |

## Example: Querying Executive Compensation

```python
import wrds
conn = wrds.Connection()

# List available tables
conn.list_tables(library='comp_execucomp')

# Get CEO compensation for S&P 500 firms
ceo_pay = conn.raw_sql("""
    SELECT gvkey, year, exec_fullname, coname, title, salary, bonus,
           stock_awards, option_awards, total_curr, tdc1
    FROM comp_execucomp.anncomp
    WHERE year >= 2019
      AND ceoann = 'CEO'
""")
```

For more examples, see the [Python API notebook](../notebook.md).
