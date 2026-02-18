# WRDS US Patents

## Overview

The WRDS US Patents dataset provides **patent-level data linked to publicly traded companies**, making it possible to study innovation and R&D output at the firm level.

**What you can find here:**

- **Patent grants**: patent number, grant date, application date, title
- **Assignees**: the firm or individual holding the patent, linked to GVKEY/PERMNO
- **Patent citations**: forward and backward citation counts
- **Patent classes**: technology classification (USPC, CPC)
- **Inventor information**: inventor names and locations

This data is widely used in research on corporate innovation, R&D productivity, and the market value of patents.

## WRDS Access

- **WRDS web interface**: <a href="https://wrds-www.wharton.upenn.edu/pages/get-data/wrds-us-patents/" target="_blank">WRDS US Patents</a>
- **Python API library**: `patent`
- **Data dictionary**: <a href="https://wrds-www.wharton.upenn.edu/data-dictionary/patent/" target="_blank">Link</a>

## Example

```python
import wrds
conn = wrds.Connection()

# List available tables
conn.list_tables(library='patent')
```

For more examples, see the [Python API notebook](../Basics%20of%20Using%20Python%20on%20WRDS%20Platform.ipynb).
