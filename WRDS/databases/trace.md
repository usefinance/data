# TRACE (Trade Reporting and Compliance Engine)

## Overview

TRACE provides **transaction-level data for the US corporate bond and agency debt market**. It is operated by FINRA and captures virtually all over-the-counter (OTC) fixed income transactions in the US.

**What you can find here:**

- **Individual bond trades**: price, yield, volume, buy/sell side, trade execution time
- **Corporate bonds**: investment grade and high yield
- **Agency debt**: government-sponsored enterprise (GSE) bonds
- **Trade reporting details**: reporting dealer, contra party type, trade type (customer vs. inter-dealer)
- **Historical coverage**: from July 2002 onwards

TRACE is the primary source for academic research on corporate bond market liquidity, pricing, and transaction costs.

## WRDS Access

- **WRDS web interface**: <a href="https://wrds-www.wharton.upenn.edu/pages/get-data/otc-corporate-bond-and-agency-debt-bond-transaction-data/trace-enhanced/bond-trades/" target="_blank">TRACE Enhanced — Bond Trades</a>
- **Python API library**: `trace`
- **Data dictionary**: <a href="https://wrds-www.wharton.upenn.edu/data-dictionary/trace/" target="_blank">Link</a>

## Key Tables

Use `conn.list_tables(library='trace')` in the Python API to see all available tables.

## Example: Querying Bond Trades

```python
import wrds
conn = wrds.Connection()

# List available tables
conn.list_tables(library='trace')

# Get recent bond trades
trades = conn.raw_sql("""
    SELECT cusip_id, trd_exctn_dt, trd_exctn_tm,
           rptd_pr, entrd_vol_qt, rpt_side_cd
    FROM trace.trace_enhanced
    WHERE trd_exctn_dt >= '2023-01-01'
    LIMIT 100
""", date_cols=['trd_exctn_dt'])
```

For more examples, see the [Python API notebook](../Basics%20of%20Using%20Python%20on%20WRDS%20Platform.ipynb).
