# GeoTrade

**Real-time geopolitical market intelligence agent.**

GeoTrade monitors global news 24/7 and detects geopolitical events as they break — conflicts, sanctions, military escalations, trade disruptions — then instantly analyzes how they affect financial markets and sends structured alerts to Discord.

## What it does

- Monitors global news every 10 minutes using NewsAPI
- Detects new geopolitical events automatically (only alerts on new headlines)
- Calculates a **Geopolitical Tension Index (GTI)** score per region (0–100, LOW/MEDIUM/HIGH/CRITICAL)
- Analyzes market impact across equities, bonds, FX, commodities, crypto, and gold
- Maps impact to a personal portfolio (VAS.AX, VGS.AX, NVDA, AAPL, MSFT, SPY, QQQ, BTC, ETH, SOL)
- Sends institutional-grade analysis to Discord with portfolio positioning recommendations

## Example Discord alert

```
🌍 GEOTRADE ALERT — GTI: 78 (HIGH)

📍 TRIGGERING EVENT
Houthi missile attack disrupts Red Sea shipping routes
Region: Middle East

📊 MARKET IMPACT
XAU/USD — Bullish (safe haven flows)
OIL — Bullish (supply disruption risk)
MSFT/NVDA — Bearish short-term (risk-off)
SPY — Watch for volatility spike

⚠️ PORTFOLIO IMPACT
Your tech-heavy portfolio is exposed. QQQ and NVDA most at risk.
Consider: trim growth, rotate to gold or energy.
```

## Setup

### 1. Install dependencies

```bash
pip install -r requirements.txt
```

### 2. Create a `.env` file

```
NEWS_API_KEY=your_newsapi_key
DISCORD_WEBHOOK_URL=your_discord_webhook_url
```

### 3. Run locally

```bash
python geotrade.py
```

### 4. Deploy to Railway

1. Push this repo to GitHub
2. Go to [railway.app](https://railway.app) and connect your repo
3. Add your environment variables in the Railway dashboard
4. Deploy — it runs 24/7 automatically

## Tech stack

- [ConnectOnion](https://connectonion.com) — agent framework
- Gemini 2.5 Pro — LLM
- NewsAPI — news source
- yfinance — real-time market data
- Discord Webhooks — alerts

## Tools

| Tool | Description |
|---|---|
| `get_global_news()` | Fetches latest geopolitical headlines |
| `get_regional_news(region)` | Fetches news for a specific region |
| `get_price(ticker)` | Gets current price and % change |
| `calculate_gti(region, news)` | Calculates geopolitical tension score |
| `send_discord_message(message)` | Sends alert to Discord |

## Disclaimer

For educational purposes only. Not financial advice.
