# Compustat Global

## Overview

Compustat Global provides **fundamental financial data, stock prices, exchange rates, and index data for companies worldwide** (excluding North America, which is covered by [Compustat North America](compustat-north-america.md)). It covers over 80 countries.

**What you can find here:**

- **Company fundamentals**: annual and quarterly income statement, balance sheet, and cash flow data for non-US/Canadian companies
- **Stock prices and returns**: daily and monthly security-level price data across global exchanges
- **Index data**: daily and monthly index values and index constituent histories
- **Exchange rates**: daily and monthly exchange rates for all covered currencies
- **Economic indicators**: monthly macroeconomic indicators by country
- **Company identifiers**: GVKEY, ISIN, SEDOL, local exchange ticker, GICS industry classification

## WRDS Access

- **WRDS web interface**: <a href="https://wrds-www.wharton.upenn.edu/pages/get-data/compustat-capital-iq-standard-poors/compustat/global-daily/" target="_blank">Compustat Global Daily</a>
- **WRDS product name**: `comp_global_daily`
- **Python API library**: `comp_global_daily`
- **Update frequency**: Daily
- **Data dictionary**: <a href="https://wrds-www.wharton.upenn.edu/data-dictionary/comp_global_daily/" target="_blank">Link</a>

## Tables

### Company Fundamentals

| Table | Description | Use case |
|-------|-------------|----------|
| `g_funda` | **Global Fundamental Annual** | Annual financial statements — the main table for global company fundamentals |
| `g_fundq` | **Global Fundamental Quarterly** | Quarterly financial statements |
| `g_funda_fncd` | Global Annual Footnote and Data Code File | Footnotes and data quality codes for annual data |
| `g_fundq_fncd` | Global Quarterly Footnote and Data Code File | Footnotes and data quality codes for quarterly data |
| `g_company` | **Company** | Company identifiers, descriptors, and industry classifications |

### Company Descriptors & Classifications

| Table | Description |
|-------|-------------|
| `g_co_aaudit` | Company Auditor |
| `g_co_adesind` | Company Annual Descriptor |
| `g_co_afnd1` / `g_co_afnd2` | Company Annual Items (A–L / M–Z) |
| `g_co_afnddc1` / `g_co_afnddc2` | Company Annual Data Codes (A–L / M–Z) |
| `g_co_afntind1` / `g_co_afntind2` | Company Annual Footnotes (A–L / M–Z) |
| `g_co_ainvval` | Company Inventory Valuation |
| `g_co_gsuppl` | Global Supplemental Items |
| `g_co_hgic` | Company GICS History |
| `g_co_iaudit` | Company Interim Auditor |
| `g_co_idesind` | Company Interim Descriptor |
| `g_co_ifndq` | Company Interim Quarterly Items |
| `g_co_ifndsa` | Company Interim Semi-Annual Items |
| `g_co_ifndytd` | Company Interim Year-to-Date Items |
| `g_co_ifntq` / `g_co_ifntsa` / `g_co_ifntytd` | Company Interim Footnotes (Quarterly / Semi-Annual / YTD) |
| `g_co_industry` | Company Industry Classification |
| `g_co_ipcd` | Company Industry Presentation |
| `g_co_offtitl` | Officer Title Codes |

### Security (Stock) Data

| Table | Description | Use case |
|-------|-------------|----------|
| `g_secd` | **Global Security Daily** | Daily stock prices, returns, and volume — the main table for global stock data |
| `g_secm` | **Global Security Monthly** | Monthly stock prices and returns |
| `g_sec_dprc` | Security Daily Price | Raw daily prices |
| `g_sec_dtrt` | Security Daily Total Return Factor | Total return factors for computing returns |
| `g_sec_divid` | Security Dividend | Dividend payments |
| `g_sec_split` | Security Stock Split | Stock split events |
| `g_sec_adjfact` | Security Cumulative Split Factor | Cumulative adjustment factors for splits |
| `g_sec_history` | Security Historical Identifiers | Historical ticker/ISIN/SEDOL changes |
| `g_security` | Security | Security master file with identifiers |

Security-level fundamental and descriptor data:

| Table | Description |
|-------|-------------|
| `g_sec_adesind` | Security Issue Annual Fundamental Descriptors |
| `g_sec_afnd` | Security Issue Annual Fundamental Data |
| `g_sec_afnddc` | Security Issue Annual Fundamental Data Codes |
| `g_sec_afnt` | Security Issue Annual Fundamental Footnotes |
| `g_sec_idesind` | Security Issue Interim Fundamental Descriptors |
| `g_sec_ifnd` | Security Interim Items |
| `g_sec_ifnt` | Security Interim Footnotes |

Monthly international security data:

| Table | Description |
|-------|-------------|
| `g_sec_gmth` | Intl Security Monthly Descriptor |
| `g_sec_gmthprc` | Intl Security Monthly Item |
| `g_sec_gmthdiv` | Intl Security Monthly Dividend |
| `g_sec_gmdivfn` | Intl Security Monthly Dividend Footnote |

### Name & Identifier Files

| Table | Description | Use case |
|-------|-------------|----------|
| `g_names` | **Global Name File** | Company identifiers: GVKEY, company name, country, ISIN, SEDOL, exchange |
| `g_namesq` | Global Name File (quarterly) | Same as above, quarterly frequency |
| `g_secnamesd` | Global Daily Security Name File | Security-level identifiers, daily |
| `g_secnamesm` | Global Monthly Security Name File | Security-level identifiers, monthly |
| `g_names_ix` | Global Index Fundamentals Name File | Index identifiers |
| `g_names_ix_cst` | Global Index Constituents Name File | Index constituent identifiers |

### Index Data

| Table | Description | Use case |
|-------|-------------|----------|
| `g_idx_daily` | **Index Daily** | Daily index price levels for global indices |
| `g_idx_mth` | **Index Monthly** | Monthly index price levels |
| `g_idx_index` | Indices | Index master file (names, codes) |
| `g_idxcst_his` | Index Constituent History | Historical membership of companies in indices |

### Exchange Rates

| Table | Description | Use case |
|-------|-------------|----------|
| `g_exrt_dly` | **Exchange Rate Daily** | Daily exchange rates for all covered currencies |
| `g_exrt_mth` | **Exchange Rate Monthly** | Monthly exchange rates |
| `g_currency` | Currency | Currency master file (codes, names) |
| `wrds_g_exrate` | WRDS Exchange Rates | WRDS-curated exchange rate data |

### Economic Indicators

| Table | Description | Use case |
|-------|-------------|----------|
| `g_ecind_desc` | Economic Indicator Descriptor | Description of available economic indicators |
| `g_ecind_mth` | Economic Indicator Monthly | Monthly macroeconomic indicators (GDP, CPI, etc.) by country |

### Reference Tables

These are lookup/reference tables for codes used across Compustat Global. Useful for decoding abbreviations and codes in the data.

| Table | Description |
|-------|-------------|
| `r_accstd` | Accounting Standards |
| `r_auditors` | Auditors |
| `r_country` | Country codes |
| `r_currency` | (via `g_currency`) |
| `r_datacode` | Data Codes |
| `r_ex_codes` | Exchange Trading System Codes |
| `r_exrt_typ` | Exchange Rate Types |
| `r_giccd` | GICS Industry Codes |
| `r_siccd` | SIC Industry Codes |
| `r_naiccd` | NAICS Industry Codes |
| `r_sectors` | S&P Sector Codes |
| `r_statesl` | States |

<details>
<summary>All reference tables</summary>

`r_accstd`, `r_acqmeth`, `r_auditors`, `r_auopic`, `r_balpres`, `r_cf_formt`, `r_coindpre`, `r_compstat`, `r_consol`, `r_co_status`, `r_country`, `r_cstclscd`, `r_datacode`, `r_datafmt`, `r_divtaxmarker`, `r_docsrce`, `r_exchgtier`, `r_ex_codes`, `r_exrt_typ`, `r_fndfntcd`, `r_footnts`, `r_foricd`, `r_giccd`, `r_hcalendr`, `r_idxclscd`, `r_inactvcd`, `r_incstats`, `r_indfmt`, `r_indsec`, `r_invval`, `r_issuetyp`, `r_majidxcl`, `r_mic_codes`, `r_naiccd`, `r_notetype`, `r_ntsubtype`, `r_offcrso`, `r_ogmethod`, `r_opinions`, `r_prc_stat`, `r_qsrcdoc`, `r_secannfn`, `r_sec_stat`, `r_sectors`, `r_siccd`, `r_spiicd`, `r_spmicd`, `r_statalrt`, `r_states`, `r_stko`, `r_titles`, `r_updates`

</details>

### Metadata Tables

| Table | Description |
|-------|-------------|
| `dd_group` | Data Group |
| `dd_group_xref` | Data Group to Item cross-reference |
| `dd_item` | Item definitions |
| `dd_package` | Package definitions |
| `xfl_column` | Data Dictionary Columns |
| `xfl_table` | Data Dictionary Tables |

## Example: Querying Global Fundamentals

```python
import wrds
conn = wrds.Connection()

# List available tables
conn.list_tables(library='comp_global_daily')

# Get annual fundamentals for a specific company
data = conn.raw_sql("""
    SELECT gvkey, datadate, conm, at, sale, ni
    FROM comp_global_daily.g_funda
    WHERE datadate >= '2019-01-01'
      AND datafmt = 'HIST_STD'
      AND consol = 'C'
      AND indfmt = 'INDL'
    LIMIT 100
""", date_cols=['datadate'])

# Get daily exchange rates for EUR/USD
exrates = conn.raw_sql("""
    SELECT datadate, tocurd, exratd
    FROM comp_global_daily.g_exrt_dly
    WHERE fromcurd = 'USD'
      AND tocurd = 'EUR'
      AND datadate >= '2023-01-01'
""", date_cols=['datadate'])
```

For more examples, see the [Python API notebook](../notebook.md).
