# Axiom-MK-II
Please check: https://asaintpi.github.io/Axiom-MK-II/ for live updates.

Axiom MK-II is a systematic, pre-market analysis engine designed to identify and rank U.S. equities with a high statistical probability of significant intraday price deviation. The system operates on a strict, time-locked forensic analysis model, reconstructing the market state as it existed at 09:15 A.M. ET on any given trading day.

The core objective is to move beyond subjective analysis by systematically quantifying the confluence of factors known to precede high-velocity price movements. The system's output is not a trade recommendation, but a ranked intelligence briefing intended to be consumed by a human operator who makes the final risk allocation decision.

2. Core Methodology
The system's analytical engine is built upon a multi-pillar, probabilistic scoring model. Each potential candidate is evaluated across three distinct factor groups, with the final score representing a confluence of a fundamental catalyst, favorable market structure, and quantifiable momentum.

The Three Pillars of Analysis:
Catalyst Potency: A score (0-10) is assigned based on the material impact of a fresh, verifiable news event. The rubric prioritizes discrete, financially significant events (e.g., FDA approvals, M&A, substantial earnings beats) over promotional announcements. NLP and entity extraction are used to classify news against a predefined scoring hierarchy.

Structural Volatility: A score (0-10) is assigned based on market-structure characteristics that influence supply and demand dynamics. This pillar is primarily driven by Public Float, where lower floats receive higher scores. A bonus is applied for exceptionally high Short Interest relative to float, identifying potential for short-squeeze-driven volatility.

Pre-Market Momentum: A score (0-10) is assigned based on the intensity of pre-market trading activity. This is a multi-factor score requiring both a significant price gap from the previous close and exceptionally high relative volume (pre-market volume as a multiple of the 30-day average daily volume).

3. Data Acquisition & Integrity
The integrity of the system's output is critically dependent on a rigorous data acquisition protocol.

Time-Locking: The system's "knowledge" is hard-capped at 09:15 A.M. ET. All data points—from news articles to pre-market trade data—are filtered by their canonical timestamps. Any data without a verifiable timestamp or with a timestamp after the cut-off is discarded.

Hierarchical Sourcing: For critical data points like Public Float and Short Interest, the system follows a strict sourcing hierarchy. It prioritizes official SEC filings (10-K, 10-Q, 20-F) and exchange-reported data. If primary sources are inaccessible or stale, it falls back to a consensus model using multiple independent financial data aggregators, and this fallback is explicitly flagged in the output.

Forensic Reconstruction: For back-testing, the system operates in a forensic mode, using its research capabilities to reconstruct the data landscape from archived news, filings, and market reports for a specific historical date.

4. Scoring, Ranking, & Tiering
Candidates that pass an initial liquidity and price filter are scored against the rubric.

Total Score: Catalyst + Structure + Momentum (Max 30)

Qualification Threshold: A total_score ≥ 12 is required for a candidate to be considered.

Ranking: Qualifying candidates are ranked descending by total_score. Ties are broken by gap_pct.

Tiering System: Each qualifying signal is assigned a tier to communicate its conviction level to the operator:

A-plus: Score ≥ 24

A-minus: Score ≥ 18

B: Score ≥ 12

