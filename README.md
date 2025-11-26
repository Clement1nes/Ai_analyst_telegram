📘 README.md
AI Financial Analyst — Automated Market Intelligence System
Real-time macro + equity + crypto sentiment workflow built in n8n, generating compressed, insight-dense Telegram briefings using GPT-4.
This system autonomously collects market data, extracts signals, interprets sentiment, builds performance charts, and sends you an AI-written daily briefing at 7AM — tailored to your risk profile, trading style & watchlist.

🚀 Features
FeatureDescription📊 Market DataYahoo Finance price feeds — indices, watchlist, currencies, crypto📰 News SentimentRSS headline scraping through Yahoo Finance News🧠 Reddit AnalysisTicker extraction, sentiment scoring, top comment filtering🔥 Trending AssetsPulls Yahoo Finance trending tickers live🧩 AI Market BriefingGPT-4 writes formatted Telegram-ready morning report📉 Heatmap GenerationWatchlist performance rendered as ASCII heatmap📡 Fully AutomatedDaily schedule trigger + configurable runtime❗ Error ProtectionTelegram alerting on workflow failure

🏗 System Architecture
Yahoo Finance → Market Data Engine → Aggregator → AI Prompt → GPT-4
Reddit JSON → Scraper → Sentiment/Ticker Parser → Aggregator → 📊 Charts → Telegram
News RSS → Parser → Headlines → Aggregator → AI/Charts → Telegram

Final output is delivered as:
📩 AI Briefing Message
📊 Watchlist Heatmap Chart
🔥 Reddit Sector Activity Breakdown
⚠️ Alerts if data fails or API drops

📥 Installation
Requirements


n8n (self-hosted or cloud)


OpenAI API key (GPT-4 recommended)


Telegram Bot Token (@BotFather)


Basic YAML/JSON config ability



⚙️ Setup


Clone repository


git clone https://github.com/<you>/<repo-name>.git



Import the workflow JSON into n8n


Configure ⚙️ Configuration node:


userProfile: {
    name: "Your Name",
    riskTolerance: "moderate",
    investmentStyle: "growth",
    focusSectors: ["Tech", "Finance"],
    watchlist: ["AAPL","MSFT","GOOGL"],
    indices: ["SPY","QQQ","DIA"],
    crypto: ["BTC-USD","ETH-USD"],
}



Add credentials:
| Credential | Used For |
|---|---|
| OpenAI API | AI summaries |
| Telegram API | Output delivery |
| (None) | Reddit uses public JSON API |


Enable schedule trigger → automated at 7am daily
(optional: change interval to 1H / 4H / weekly)



📬 Output Example
📊 FINANCIAL ANALYST DAILY BRIEFING
📅 Monday, January 12

🌅 Market opens mixed — tech rotation + soft USD.
📊 SPY +0.74%  | QQQ +1.02% | BTC flat → low vol.

💼 Watchlist Focus
AAPL +2.1% — earnings bullish flow
NVDA +4.8% — retail volume surge
TSLA -1.4% — bearish Reddit skew

🔥 Opportunities
• AI chips + cloud momentum breakout
• Crypto rotation forming → ETH stronger relative

⚠ Risks:
Bond volatility creeping → possible risk-off later

Delivered via Telegram in < 4000 characters, auto-split if longer.

🗺 Roadmap


🚨 Intraday execution alerts


🧾 PDF market reports


🧠 LLM memory + ongoing state tracking


🔗 Plug-in exchange API integration (Binance / Alpaca / IBKR)



🤝 Contribute
Pull requests welcome.
Add new data feeds, sentiment engines, chart formats or ML pipelines.

⭐ If this helped — star the repo!

Would you like me to generate:
📌 Repo banner
📌 Badges (Build status / Version / Made with n8n / GPT-4)
📌 A Logo for AI Analyst
📌 GitHub Wiki documentation
Reply yes and choose one.
