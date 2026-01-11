📊 Trader Behavior Analysis Under Bitcoin Market Sentiment
👋 Introduction

This project explores how Bitcoin market sentiment (Fear & Greed Index) influences trader behavior, risk-taking, and performance using real historical trading data from Hyperliquid.

Instead of only looking at profit and loss, the analysis focuses on behavioral patterns — how emotions like fear and greed affect leverage usage, risk exposure, and overall trading decisions.

The goal is to provide practical insights that can help trading teams and risk managers make smarter, sentiment-aware decisions.

🎯 Project Objective

The main objectives of this project are:

Understand how market sentiment impacts trader performance

Analyze changes in risk exposure during Fear vs Greed phases

Identify signs of emotional or overconfident trading

Build a robust and reproducible analysis pipeline using real-world crypto data

📂 Datasets Used
1️⃣ Historical Trader Data (Hyperliquid)

This dataset contains trade-level information such as:

Account address

Coin / symbol

Execution price

Trade timestamp

Closed PnL

Leverage (when available)

Note: Like most real trading datasets, column names and availability vary.
The analysis is designed to adapt automatically instead of relying on fixed schemas.

2️⃣ Bitcoin Fear & Greed Index

This dataset represents daily Bitcoin market sentiment categorized into:

Extreme Fear

Fear

Neutral

Greed

Extreme Greed

Each trading day is mapped to a corresponding market emotion.

🧠 Approach & Methodology
🔹 Data Preparation

Automatically detected timestamp, PnL, and price columns

Converted UNIX timestamps to readable datetime format

Created a common trade_date field for daily sentiment mapping

🔹 Real-World Data Handling

Crypto datasets often miss important fields such as:

Trade size

Leverage

Instead of forcing assumptions or failing the pipeline:

A normalized size proxy is used when size is unavailable

Trades are treated as spot-equivalent (leverage = 1) when leverage is missing

All assumptions are clearly documented for transparency.

🧮 Feature Engineering

The following features were engineered:

Absolute PnL – captures volatility without trade direction

Trade Value – execution price × trade size (real or inferred)

Risk Exposure – trade value × leverage

Win/Loss Flag – identifies profitable vs losing trades

⭐ Behavioral Risk Score (Unique Contribution)

A custom Behavioral Risk Score was created to quantify how aggressive or emotional a trade is.

This score combines:

Leverage usage

Risk exposure

Trade volatility

Higher scores indicate riskier, potentially emotion-driven trading behavior.

This metric helps move beyond simple profit analysis into behavioral finance insights.

📊 Analysis Performed

PnL distribution across different sentiment phases

Comparison of risk exposure during Fear vs Greed

Behavioral Risk Score analysis by sentiment

Aggregated performance summaries

Statistical validation using the Kruskal–Wallis test

📈 Key Insights

Traders tend to increase risk exposure during Greed and Extreme Greed

Extreme Greed often shows higher risk-taking but weaker median returns, suggesting overconfidence

Fear periods are associated with fewer trades and more disciplined behavior

Market sentiment has a statistically significant impact on trader performance

💡 Business Impact

These insights can help trading teams:

Apply stricter risk controls during euphoric market conditions

Detect emotionally driven over-trading early

Improve long-term capital preservation

Design sentiment-aware trading and risk strategies

▶️ How to Run the Project
1️⃣ Clone the Repository
git clone <>
cd Trader-Behavior-Insights

2️⃣ Install Dependencies
pip install -r requirements.txt

3️⃣ Run the Notebook

Open and run:

Trader_Behavior_Sentiment_Analysis.ipynb

Recommended:

Restart the kernel

Run all cells sequentially

⚠️ Assumptions & Limitations

When trade size is missing, a normalized proxy is used

When leverage is unavailable, leverage is assumed to be 1 (spot-equivalent)

Analysis is based on historical data and does not predict future performance

These assumptions reflect real-world trading analytics practices.

🚀 Future Improvements

Account-level behavioral profiling

Strategy backtesting using sentiment signals

Time-series modeling of sentiment transitions

Integration with real-time trading data

👤 Author

Harsh Thanki
Junior Data Scientist
Focused on Data Science, AI/ML, and Trading Analytics
