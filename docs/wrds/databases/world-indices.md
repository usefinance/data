# World Indices

## Overview

The WRDS World Indices dataset provides **daily and monthly price data for major stock market indices worldwide**.

**What you can find here:**

- **Index price levels**: daily and monthly closing values
- **Index returns**: price returns and total returns
- **Global coverage**: indices from markets across the Americas, Europe, Asia-Pacific, and emerging markets
- **Historical data**: long time series for major indices

## WRDS Access

- **WRDS web interface**: <a href="https://wrds-www.wharton.upenn.edu/pages/get-data/world-indices-wrds/" target="_blank">World Indices</a>
- **Python API library**: `wi`
- **Data dictionary**: <a href="https://wrds-www.wharton.upenn.edu/data-dictionary/wi/" target="_blank">Link</a>

## Example

```python
import wrds
conn = wrds.Connection()

# List available tables
conn.list_tables(library='wi')
```

For more examples, see the [Python API notebook](../notebook.md).
