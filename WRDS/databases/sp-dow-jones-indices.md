# S&P Dow Jones Indices

## Overview

The Historical S&P Dow Jones Indices dataset on WRDS provides **historical index-level data for S&P and Dow Jones indices**, including the S&P 500, S&P 400, S&P 600, and Dow Jones Industrial Average.

**What you can find here:**

- **Index levels**: daily closing values for S&P and Dow Jones indices
- **Index returns**: price returns and total returns (including dividends)
- **Constituent data**: historical index membership (which companies were in the S&P 500 at any point in time)
- **Sector indices**: S&P sector and industry-level indices

This data is commonly used for benchmarking, studying index effects (additions/deletions), and constructing market return series.

## WRDS Access

- **WRDS web interface**: <a href="https://wrds-www.wharton.upenn.edu/pages/get-data/historical-sp-dow-jones-indices-spdji/" target="_blank">Historical S&P Dow Jones Indices</a>
- **Python API library**: `spdji`
- **Data dictionary**: <a href="https://wrds-www.wharton.upenn.edu/data-dictionary/spdji/" target="_blank">Link</a>

## Example

```python
import wrds
conn = wrds.Connection()

# List available tables
conn.list_tables(library='spdji')
```

For more examples, see the [Python API notebook](../Basics%20of%20Using%20Python%20on%20WRDS%20Platform.ipynb).
