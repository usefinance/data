# Cryptocurrency & Digital Asset Data

Free and open-access data sources for cryptocurrency market prices, index data, and exchange data.

## Market Price Data

- <a href="https://www.coingecko.com/en/api" target="_blank">CoinGecko API</a> <span class="badge badge-api">API</span> <span class="badge badge-python">Python</span> <span class="badge badge-global">Global</span> <span class="badge badge-crypto">Crypto</span> — Free API for current and historical cryptocurrency market data, including prices, market cap, trading volume, and exchange data for 10,000+ coins. Historical OHLCV data available. Free tier supports up to 30 calls/minute with no API key required; a free account unlocks higher limits (up to 10,000–30,000 calls/month). Python access via <a href="https://pypi.org/project/pycoingecko/" target="_blank">`pycoingecko`</a>. (<a href="https://github.com/man-c/pycoingecko" target="_blank">GitHub</a>)

```bash
pip install pycoingecko
```

- <a href="https://coinmarketcap.com/api/" target="_blank">CoinMarketCap API</a> <span class="badge badge-api">API</span> <span class="badge badge-global">Global</span> <span class="badge badge-crypto">Crypto</span> — Free Basic plan with up to 10,000 credits/month (~333 calls/day) covering current price, market cap, and supply data for 9 endpoints. API key required (free registration). Note: historical data is not available on the free tier.

- <a href="https://www.royalton-crix.com/" target="_blank">Royalton CRIX</a> <span class="badge badge-csv">CSV</span> <span class="badge badge-global">Global</span> <span class="badge badge-crypto">Crypto</span> — The CRIX (CRyptocurrency IndeX) is a market-index for the cryptocurrency market, developed at Humboldt University Berlin and now calculated by S&P Global. Also includes the VCRIX volatility index. Last 90 days freely downloadable as CSV; longer historical series (from March 2018) via subscription. Not for commercial use.

## Exchange & Trading Data

- <a href="https://github.com/ccxt/ccxt" target="_blank">CCXT</a> <span class="badge badge-api">API</span> <span class="badge badge-python">Python</span> <span class="badge badge-global">Global</span> <span class="badge badge-crypto">Crypto</span> — Open-source Python/JavaScript/PHP library providing a unified interface to 100+ cryptocurrency exchange APIs. Supports fetching order books, OHLCV data, trades, and more. The standard tool for programmatic access to live and historical exchange data — data availability and history depth depend on each exchange's own API. (<a href="https://pypi.org/project/ccxt/" target="_blank">PyPI</a>)

```bash
pip install ccxt
```

- <a href="https://data.binance.vision/" target="_blank">Binance Public Data</a> <span class="badge badge-csv">CSV</span> <span class="badge badge-global">Global</span> <span class="badge badge-crypto">Crypto</span> — Free bulk downloads of historical trading data from Binance. Covers klines (OHLCV), trades, and aggregate trades at tick, minute, hourly, and daily frequencies. Data available from 2017 onwards. No registration required.

- <a href="https://docs.hydromancer.xyz/reservoir" target="_blank">Hydromancer Reservoir</a> <span class="badge badge-global">Global</span> <span class="badge badge-crypto">Crypto</span> — Free archive of historical Hyperliquid exchange data, published as Parquet files (updated daily) in a requester-pays AWS S3 bucket (`s3://hydromancer-reservoir`, region ap-northeast-1). Covers trade fills (including liquidations, ADL and TWAP fills), 1-second candles, daily position snapshots and order books. No API key needed, but an AWS account is required and the requester pays AWS data transfer. Files can be queried directly with DuckDB. Licensed CC BY 4.0 (credit Hydromancer).

## On-Chain & Blockchain Data

- <a href="https://www.blockchain.com/explorer/api/blockchain_api" target="_blank">Blockchain.com API</a> <span class="badge badge-api">API</span> <span class="badge badge-global">Global</span> <span class="badge badge-crypto">Crypto</span> — Free API for Bitcoin blockchain data including transaction details, block data, address balances, and aggregate market statistics (hash rate, difficulty, mempool). No API key required for basic endpoints.

---
**See also**: [Asset Classes](assets/index.md) for an overview of all asset class data | [Python Tools & Books](python-tools.md) for yfinance (covers crypto via Yahoo Finance) and Alpha Vantage (covers crypto market data).
