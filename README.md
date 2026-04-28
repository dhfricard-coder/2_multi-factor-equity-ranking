# 2_multi-factor-equity-ranking
### **Objective:** Build a systematic stock ranking system using fundamental and technical factors, with rigorous backtesting.

**Data:** Simfin (free fundamental data), yfinance (prices), WRDS (if you can get academic access — highly recommended).

**Methodology:**

- Construct factors: Value (EV/EBIT, P/FCF), Quality (ROIC, gross margin stability, Piotroski F-score), Momentum (12-1M price momentum), Low Volatility (realised vol rank)
- Winsorise, neutralise for sector, compute z-scores
- Combine into composite score; rank universe monthly
- Backtest: Long top quintile, short bottom quintile (or long-only version)
- Compute: Sharpe, max drawdown, factor attribution, turnover-adjusted returns

**Risk framework:** Sector/market cap neutrality; factor crowding monitor (cross-sectional dispersion); transaction cost model (assume 10bps round-trip for large cap).

**AI use:** Use NLP (via Hugging Face or Claude API) to score earnings call transcripts for sentiment/quality of management commentary. Add as a soft signal layer. Fully explainable: you define the scoring rubric; AI applies it at scale.

**Stack:** Python, Colab, Simfin API, yfinance, pandas, matplotlib, GitHub.

**Output:** Backtested strategy report with full tearsheet (use pyfolio or build your own).
