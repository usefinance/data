# Fama-French Portfolios and Factors

## Overview

The Fama-French dataset on WRDS provides **factor returns, research portfolios, and liquidity factors** sourced from Kenneth French's website and other academic sources. This is the standard dataset for asset pricing research using the Fama-French three-factor and five-factor models.

**What you can find here:**

- **Factor returns**: market, size (SMB), value (HML), profitability (RMW), investment (CMA), and momentum (Mom) — daily and monthly
- **Research portfolios**: 6 portfolios (2×3) and 25 portfolios (5×5) sorted on size and book-to-market
- **Industry portfolios**: 12-industry and 48-industry classifications
- **Liquidity factors**: Pastor-Stambaugh and Sadka liquidity factors
- **China factors**: Fama-French factors for China
- **Date range**: 1926–present (updated daily)

## WRDS Access

- **WRDS web interface**: <a href="https://wrds-www.wharton.upenn.edu/pages/get-data/fama-french-portfolios-and-factors/" target="_blank">Fama-French Portfolios and Factors</a>
- **Python API library**: `ff`
- **Postgres schema**: `ff_all`
- **Data dictionary**: <a href="https://wrds-www.wharton.upenn.edu/data-dictionary/ff_all/" target="_blank">Link</a>
- **WRDS Cloud path**: `/wrds/ff/sasdata/*.*`

## Tables

| Table | Description | Frequency |
|-------|-------------|-----------|
| `factors_daily` | Market, SMB, HML, Mom | Daily |
| `factors_monthly` | Market, SMB, HML, Mom | Monthly |
| `fivefactors_daily` | Market, SMB, HML, RMW, CMA, Mom | Daily |
| `fivefactors_monthly` | Market, SMB, HML, RMW, CMA, Mom | Monthly |
| `portfolios` | 6 portfolios (2×3) on size and book-to-market | Monthly |
| `portfolios_d` | 6 portfolios (2×3) on size and book-to-market | Daily |
| `portfolios25` | 25 portfolios (5×5) on size and book-to-market | Monthly |
| `industry12` | 12-industry classification | — |
| `industry48` | 48-industry classification | — |
| `liq_ps` | Pastor-Stambaugh liquidity factors | Monthly |
| `liq_sadka` | Sadka liquidity factors | Monthly |
| `factors_china` | Fama-French factors for China | — |

## Example

```python
import wrds
conn = wrds.Connection()

# List available tables
conn.list_tables(library='ff')

# Get monthly Fama-French 5 factors + momentum
factors = conn.raw_sql("""
    SELECT date, mktrf, smb, hml, rmw, cma, mom, rf
    FROM ff_all.fivefactors_monthly
    WHERE date >= '2020-01-01'
""", date_cols=['date'])

# Get daily 3 factors + momentum
factors_daily = conn.raw_sql("""
    SELECT date, mktrf, smb, hml, mom, rf
    FROM ff_all.factors_daily
    WHERE date >= '2024-01-01'
""", date_cols=['date'])

# Get Pastor-Stambaugh liquidity factors
liquidity = conn.raw_sql("""
    SELECT *
    FROM ff_all.liq_ps
    WHERE date >= '2020-01-01'
""", date_cols=['date'])
```

For more examples, see the [Python API notebook](../Basics%20of%20Using%20Python%20on%20WRDS%20Platform.ipynb).
