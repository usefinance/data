# Subsidiary Data

## Overview

The WRDS Subsidiary dataset provides **parent–subsidiary ownership relationships** for publicly traded US companies, derived from SEC Exhibit 21 filings.

**What you can find here:**

- **Subsidiary names**: names of subsidiaries owned by public companies
- **Parent companies**: the publicly traded parent (linked by CIK/GVKEY)
- **Jurisdiction**: state or country of incorporation of each subsidiary
- **Ownership structure**: which entities own which subsidiaries

This data is useful for research on corporate structure, multinational operations, tax planning, and geographic footprint analysis.

## WRDS Access

- **WRDS web interface**: <a href="https://wrds-www.wharton.upenn.edu/pages/get-data/subsidiary-data-wrds/" target="_blank">Subsidiary Data</a>
- **Python API library**: `subdiary`
- **Data dictionary**: <a href="https://wrds-www.wharton.upenn.edu/data-dictionary/subdiary/" target="_blank">Link</a>

## Example

```python
import wrds
conn = wrds.Connection()

# List available tables
conn.list_tables(library='subdiary')
```

For more examples, see the [Python API notebook](../notebook.md).
