# PSX Signal Pro — mobile web starter

A no-build, phone-friendly static web app for PSX technical-analysis practice.

## Included
- Sample data mode (synthetic and clearly labelled; NEVER trade from it)
- CSV import for OHLCV data
- EMA 12/26, RSI 14, MACD and volume comparison
- Explainable BUY SETUP / SELL-EXIT SETUP / WAIT rule
- Position sizing calculator using account risk and stop-loss
- Simplified EMA crossover backtest with costs, buy-and-hold comparison and drawdown estimate
- Optional experimental compatible API connector

## Run on your phone
1. Extract this ZIP or open `index.html` in a browser. Some Android file managers block scripts from local files; if so, use the hosting steps below.
2. Easiest hosting: create a free Replit HTML/CSS/JS project or a GitHub repository, upload `index.html`, then deploy it as a static site (GitHub Pages / Replit static web deployment).
3. Open the published URL in Chrome. Use Chrome menu → **Add to Home screen** to make an app-like shortcut.

## Importing data
CSV must contain a header row with these columns (case-insensitive):
`Date,Open,High,Low,Close,Volume`
Rows should be ordered or sortable by date. Use actual daily candles for swing trading. For intraday use genuine intraday candle rows with timestamps in `Date`; do not treat daily data as intraday.

## Data and API caveats
- This starter does not ship with verified live data credentials or a guaranteed live PSX feed.
- API mode is experimental and expects `GET {base}/stocks/{SYMBOL}/historical` returning a JSON array (or `data` / `results` / `history` array) of objects with date/open/high/low/close/volume fields. Many providers differ; adapt the response mapper to your provider. Browser CORS must be enabled.
- Do not put private API keys in frontend code. Use a backend proxy for secret keys.
- PSX says use or redistribution of its market data in applications may require a license/authorization. Ask PSX or an authorized vendor about personal-use terms and data rights before deploying publicly: https://www.psx.com.pk/psx/product-and-services/data-services-vending
- The app does not place trades and does not connect to a broker.
- Signals are technical rules, not a promise of accuracy or individualized investment advice. Backtest has simplified fills and omits dividends, corporate actions, liquidity, price limits, taxes, and realistic slippage. Test out-of-sample and paper trade first.

## Project structure
- `index.html` — complete frontend, no build tools required
- `README.md` — setup, data format and limitations
- `sample_ohlcv.csv` — explicitly synthetic sample CSV for testing import
