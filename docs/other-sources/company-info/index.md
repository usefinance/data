# Firm Data

Resources for identifying companies, accessing regulatory filings and financial statements, retrieving annual reports, measuring AI and data intensity, and linking firm-level data across databases.

| Topic | Description |
|-------|-------------|
| [Company Filings (SEC EDGAR)](filings.md) | SEC financial statements, filings, insider transactions, fund holdings |
| [Annual Reports](../annual-reports.md) | PDF annual reports for large global companies |
| [Identifiers & Data Linking](../identifiers.md) | CIK, GVKEY, CUSIP, ISIN — how to link datasets across sources |

## Industry Classification

### Hoberg & Phillips — Text-Based Network Industry Classifications (TNIC)

<a href="https://hobergphillips.tuck.dartmouth.edu/" target="_blank">Hoberg & Phillips</a> <span class="badge badge-csv">CSV</span> <span class="badge badge-us">US</span> — Text-Based Network Industry Classifications (TNIC) and product market similarity scores derived from 10-K product description text. Covers U.S. public firms. Widely used as an alternative to SIC and NAICS codes for measuring industry competition, product differentiation, and peer firm identification. (<a href="https://hobergphillips.tuck.dartmouth.edu/industrydat.htm" target="_blank">Data download</a>)

The TNIC approach classifies firms into industries based on the similarity of their product descriptions in annual 10-K filings, rather than using fixed codes assigned by regulatory agencies. This allows industries to evolve over time as firm product portfolios change, and captures competitive relationships that SIC/NAICS codes miss.

A new Embeddings-based TNIC (ETNIC) is available in a preliminary release. (<a href="https://hobergphillips.tuck.dartmouth.edu/tnic_doc2vec.html" target="_blank">Data download</a>)

**Key references**:

- Hoberg, G. and Phillips, G. (2010). Product Market Synergies and Competition in Mergers and Acquisitions: A Text-Based Analysis. *Review of Financial Studies*, 23(10), 3773–3811.
- Hoberg, G. and Phillips, G. (2016). Text-Based Network Industries and Endogenous Product Differentiation. *Journal of Political Economy*, 124(5), 1423–1465.
- Hoberg, G. and Phillips, G. (2024). Scope, Scale and Competition: The 21st Century Firm. *Journal of Finance*, 80(1), 415-466.

## AI, Innovation & Data Intensity

### AI Computational Capacity & Data Intensity — Firm-Year Panel

<a href="https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi:10.7910/DVN/DJASWD" target="_blank">AI Intensity and Data Intensity: Firm-Year Panel for "Is It AI or Data That Drives Firm Market Power?"</a> <span class="badge badge-us">US</span> — Public panel from Roxana Mihet, Kumar Rishabh, and Orlando Gomes (2026), *Journal of Monetary Economics*, 157, 103878. Covers **12,038 U.S. listed firms** in CRSP-Compustat over fiscal years **2000–2023**, with **114,822 firm-year observations**. Contains two measures:

- **`ai_compute_intensity`** — Patent-based score of AI computational capacity, called "AI intensity" in the paper.
- **`data_intensity`** — Score of reliance on large datasets, constructed from 10-K business-description similarity and AI patent shares, called "Data intensity" in the paper.

Merge using **`gvkey`** and **`fyear`**. Version 1.0 contains the **March 2025 vintage** used for the paper's results, distributed as a tabular file with a README explaining construction and definitions. Compustat supplies identifiers and company names only; **no financial variables are included**. Released under CC0 1.0. (<a href="https://doi.org/10.1016/j.jmoneco.2025.103878" target="_blank">Related paper</a>)

!!! note "Measure definitions across releases"
    The JME panel's patent-based `ai_compute_intensity` measure and the AI-intensity index in the RCFS release below are distinct measures. Consult the JME README for their relationship before comparing or combining the releases.

### Cyberrisk and AI Firms — Public AI-Intensity Data

<a href="https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi:10.7910/DVN/JBVHSB" target="_blank">Replication Data for: Cyberrisk and AI Firms</a> — Public firm-year AI-intensity data from the paper by Kumar Rishabh, Roxana Mihet, and Julian Jang-Jaccard, accepted at the *Review of Corporate Finance Studies*. The Harvard Dataverse release (Version 1.0, 2026) also includes source data for the published figures and code for the regression tables and figures. Released under CC0 1.0.

!!! info "Public data and replication limits"
    The merged CRSP-Compustat/WRDS regression panel and other licensed inputs are not redistributed. A separate synthetic firm-year panel is included to run the code and check the table and figure structure; it does not reproduce the empirical results from the licensed data.

---
**See also**: [Data Collections](../researcher-data.md) for general-purpose data repositories | [WRDS](../../wrds/index.md) for Compustat and other company-level databases.
