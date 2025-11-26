
AI Financial Analyst — Automated Market Intelligence System
Real-time macro + equity + crypto sentiment workflow built in n8n, generating compressed, insight-dense Telegram briefings using GPT-4.
This system autonomously collects market data, extracts signals, interprets sentiment, builds performance charts, and sends you an AI-written daily briefing at 7AM — tailored to your risk profile, trading style & watchlist.

🚀 Features
FeatureDescription📊
Market Data
Yahoo Finance price feeds — indices, watchlist, currencies, crypto📰 News Sentiment
RSS headline scraping through Yahoo Finance News🧠 Reddit Analysis
Ticker extraction, sentiment scoring, top comment filtering🔥 
Trending Assets
Pulls Yahoo Finance trending tickers live

🧩 AI Market Briefing
GPT-4 writes formatted Telegram-ready morning report
📉 Heatmap Generation
Watchlist performance rendered as ASCII heatmap📡 
Fully AutomatedDaily schedule trigger + configurable runtime


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

🧠 Customising the AI Analyst With Prompts

This workflow is designed to be fully AI-tunable — meaning you can change the tone, style, depth, risk-focus and output structure by simply modifying one node:

Node to Edit:

📎 ✍️ Prepare AI Prompt → prompt string

This is where GPT-4 is instructed how to think, what to prioritise, and how to format the final briefing.

🔥 How to Customise the AI Output
You want it more…	Change in Prompt
Technical / Quant Heavy	Add TA focus, macro data priority, volatility analysis
Retail-Friendly	Increase simplicity + reduce jargon
Aggressive Alpha Seeking	Tell it to highlight momentum breakouts, earnings volatility
Risk-Controlled	Emphasize drawdown risk, macro uncertainty alerts
News-Driven	Increase importance of headlines & cross-market impact
Shorter Output	Lower word count / bullet structure
Longer & Deep Analysis	Raise detail caps + enable expansion sections

🔧 Example Prompt Modifications
1) More Quantitative + Institutional Tone
+ Prioritise volatility regime, liquidity trend, macro drivers.
+ Include implied volatility references if VIX rises >5%.
+ Highlight divergence between price & sentiment as a risk signal.
+ If trends conflict, emphasize caution > opportunity.

2) More Retail, Simpler & Punchier for Telegram
+ Reduce analysis to clearest 3 takeaways.
+ Replace jargon with human language: "uptrend gaining energy" > "momentum acceleration".
+ Headlines should affect portfolio decisions directly.

3) Crypto-Heavy Mode
+ Weight crypto movements equal to equities.
+ Detect BTC dominance shifts + risk-rotation signals.
+ Mention on-chain activity if included later.

4) AI Reads Like a Hedge Fund Morning Meeting
+ Write like a PM briefing analysts with position implications.
+ Include scenarios, if-else market reactions, possible flows.
+ Close with forward-looking positioning framework.

🧠 How to Prompt AI Live

You can also override the behaviour dynamically (without editing code) using instruction injections:

Method A — Modify Prepare AI Prompt node text before run

Change summary structure, tone, risk alerts, section ordering etc.

Method B — Add a Custom Directive field to config

Example:

config.userProfile.customInstruction = 
"Focus strongly on currency volatility & macro until further notice.";


Then inject into prompt:

+ Custom Instruction: ${profile.customInstruction}

Method C — Toggle output behaviour with boolean flags
analysis: {
   enable_macro_priority: true,
   include_long_form_technical: false,
   short_output_mode: true
}


Modify prompt to respond conditionally:

+ If short_output_mode = true → compress to <2000 chars max.
+ If enable_macro_priority = true → start with rates, CPI, yields, USD.

⚡Example Full Override Prompt You Can Paste In
Rewrite briefing with:
- Institutional tone similar to Goldman/JP morning notes.
- Clear bullish/bearish stance on each watchlist item.
- Highlight only 2 highest-conviction ideas.
- Reduce emojis by 50%.
- End with forward-looking catalysts in next 48H.


Paste → run → instant change in report behaviour.

🤝 Contribute
Pull requests welcome.
Add new data feeds, sentiment engines, chart formats or ML pipelines.

⭐ If this helped — star the repo!
