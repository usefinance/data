# OTC Markets

## Overview

OTC Markets Group data on WRDS provides **information on securities traded on OTC (over-the-counter) markets**, covering companies that are not listed on major exchanges like NYSE or NASDAQ.

**What you can find here:**

- **OTC-traded securities**: company and security information for OTC-listed firms
- **Market tiers**: OTCQX (highest quality), OTCQB (venture market), Pink (speculative)
- **Trading data**: prices and volume for OTC-traded securities
- **Company disclosures**: financial reporting status and disclosure levels

## WRDS Access

- **WRDS web interface**: <a href="https://wrds-www.wharton.upenn.edu/pages/get-data/otc-markets-group/" target="_blank">OTC Markets Group</a>
- **Python API library**: `otc`
- **Data dictionary**: <a href="https://wrds-www.wharton.upenn.edu/data-dictionary/otc/" target="_blank">Link</a>

## Example

```python
import wrds
conn = wrds.Connection()

# List available tables
conn.list_tables(library='otc')
```

For more examples, see the [Python API notebook](../Basics%20of%20Using%20Python%20on%20WRDS%20Platform.ipynb).
