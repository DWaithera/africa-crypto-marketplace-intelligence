Africa Crypto Market Intelligence System (MEPS)**


Overview
A data-driven analytics system that evaluates and ranks African countries based on their attractiveness for crypto exchange expansion.
It combines macroeconomic indicators, digital infrastructure metrics, and crypto market signals into a single composite index:


Market Expansion Priority Score (MEPS)
This score helps crypto exchanges and fintech companies identify where to expand, where demand exists.


Business Problem
Crypto exchanges entering African markets lack a unified framework to assess:
    Where real crypto demand exists
    Which countries have usable financial infrastructure
    Where adoption is most likely to scale
    Which markets are economically viable for expansion


Key Question
Which African markets should a crypto exchange prioritize for expansion based on measurable demand, infrastructure readiness, and adoption signals?


Solution
This project builds a multi-factor scoring system (MEPS) that ranks countries using structured data across 6 dimensions:
    Demand	Google Trends interest in crypto assets

    Adoption	Crypto adoption indicators (Chainalysis proxy)

    Infrastructure	Mobile money + internet penetration

    Financial Access	Banked population / financial inclusion

    Market Size	GDP per capita + remittance flows

    Digital Readiness	Smartphone + internet penetration

System Architecture

     Global Crypto Markets
             (CoinGecko API: BTC, ETH, USDT)
                          ↓
                  Market Sentiment Layer                          
                          ↓
                    Feature Engineering
                          ↓
                 Normalization (0–1 scaling)
                          ↓
                 Weighted Scoring Model
                          ↓
                 MEPS Country Ranking Output

                
Tech Stack
    Python (Core engine)
    Pandas (Data manipulation)
    NumPy (Numerical processing)
    Matplotlib / Seaborn (Visualization)
    CoinGecko API (Crypto market data)
    Google Trends (Demand signals)
    World Bank / GSMA datasets (macro indicators)
    Jupyter Notebook (analysis workflow)


Project Structure
Africa-Crypto-Market-Intelligence/
        │
        ├── data/
        │   ├── raw/               # API pulls & external datasets
        │   ├── processed/         # cleaned datasets
        │
        ├── notebooks/
        │   ├── 01_data_ingestion.ipynb
        │   ├── 02_feature_engineering.ipynb
        │   ├── 03_meps_model.ipynb
        │
        ├── visuals/
        │   ├── rankings.png
        │   ├── correlation_heatmap.png
        │
        ├── reports/
        │   ├── final_insights.pdf
        │
        ├── src/
        │   ├── data_pipeline.py
        │   ├── feature_engineering.py
        │   ├── meps_model.py
        │
        ├── README.md
        └── requirements.txt


MEPS Model

The Market Expansion Priority Score is calculated as:
MEPS =
    (w1 × Demand Score) +
    (w2 × Adoption Score) +
    (w3 × Infrastructure Score) +
    (w4 × Financial Access Score) +
    (w5 × Market Size Score) +
    (w6 × Digital Readiness Score)


Default Weights
    Factor	Weight
    Demand	25%
    Adoption	20%
    Infrastructure	20%
    Market Size	15%
    Financial Access	10%
    Digital Readiness	10%


Output Example

Country Rankings (MEPS Score)
    1. Nigeria 🇳🇬 → 0.92
    2. South Africa 🇿🇦 → 0.87
    3. Kenya 🇰🇪 → 0.83
    4. Ghana 🇬🇭 → 0.69


Key Insights
    Countries with strong mobile money ecosystems outperform in crypto adoption potential
    Demand signals (Google Trends) strongly correlate with transaction volume proxies
    Infrastructure readiness is a gating factor for exchange expansion
    Market size alone does not guarantee crypto adoption


Visualizations
    Country MEPS ranking bar chart
    Correlation heatmap of indicators
    Demand vs adoption scatter plots
    Infrastructure readiness comparison


How to Run This Project
    git clone https://github.com/yourusername/africa-crypto-meps.git
    cd africa-crypto-meps
    pip install -r requirements.txt
    jupyter notebook


Run notebooks in order:
    Data ingestion
    Feature engineering
    MEPS model
    Visualization


Limitations
    Uses proxy indicators where direct crypto adoption data is unavailable
    Weights are initially heuristic (can be optimized using PCA or regression)
    Informal crypto activity is not fully captured
    Data availability varies across countries


Future Improvements
    Automate Google Trends ingestion pipeline
    Add real-time CoinGecko streaming layer
    Replace heuristic weights with ML-learned weights
    Build interactive Power BI dashboard
    Expand to 20+ African markets


Author
    Damaris Waithera
    Data Analyst | Nairobi, Kenya
    GitHub: https://github.com/DWaithera
    LinkedIn: https://www.linkedin.com/in/damariswaithera/
