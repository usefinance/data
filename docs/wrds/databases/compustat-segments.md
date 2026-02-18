# Compustat Historical Segments

## Overview

Compustat Historical Segments provides **business and geographic segment-level data** for companies covered by Compustat. Under accounting standards (SFAS 131 / IFRS 8), companies must report financial data broken down by operating segments and geographic regions.

**What you can find here:**

- **Business segment data**: revenue, operating profit, assets, capital expenditures, and depreciation by business segment
- **Geographic segment data**: revenue and assets by geographic region (e.g., domestic vs. international, or by country/region)
- **Segment identifiers**: segment name, SIC code, and type (business vs. geographic)

This data is useful for studying corporate diversification, geographic revenue exposure, and segment-level performance.

## WRDS Access

- **WRDS web interface**: <a href="https://wrds-www.wharton.upenn.edu/pages/get-data/compustat-capital-iq-standard-poors/compustat/historical-segments-daily/" target="_blank">Compustat Historical Segments Daily</a>
- **WRDS product name**: `comp_segments_hist_daily`
- **Python API library**: `comp_segments_hist_daily`
- **Update frequency**: Daily
- **Data dictionary**: <a href="https://wrds-www.wharton.upenn.edu/data-dictionary/comp_segments_hist_daily/" target="_blank">Link</a>

## Tables

Use `conn.list_tables(library='comp_segments_hist_daily')` to see the full list of available tables.

## Example: Querying Segment Data

```python
import wrds
conn = wrds.Connection()

# List available tables
conn.list_tables(library='comp_segments_hist_daily')
```

For more examples, see the [Python API notebook](../notebook.md).
