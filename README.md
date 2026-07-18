# SmartCentres REIT Investment Analysis

## Project Overview
This project evaluates **SmartCentres Real Estate Investment Trust (SRU.UN)** from the perspective of a potential investor. It combines financial performance data, stock market data, macroeconomic indicators, and competitor analysis to produce an evidence-based investment recommendation.

This project was completed for **BSMM-8730 – Data Acquisition and Management**, University of Windsor, Master of Management.

## Business Problem
A potential investor wants to determine whether SmartCentres REIT is a suitable investment. This requires analyzing historical stock performance, dividend sustainability, financial performance, competitor performance, and macroeconomic indicators such as interest rates, in order to support an evidence-based investment recommendation.

## Team
| Name | Role |
|---|---|
| Pradeepta Kumar Saha | |
| | |
| | |

## Data Sources
- [SmartCentres REIT](https://smartcentres.com/) — property portfolio, financial reports, distributions
- [Bank of Canada / Valet API](https://www.bankofcanada.ca/valet-api-how-to/) — interest rates and macroeconomic indicators
- [yfinance](https://pypi.org/project/yfinance/) — historical stock prices and dividend data
- [WOWA](https://wowa.ca/reit-canada) — Canadian REIT competitor comparison data
- [SEDAR+](https://www.sedarplus.ca/) — regulatory filings

## Repository Structure
```
8730-assignment-main/
├── README.md
├── .gitignore
├── 01_smartcentres_scraping.ipynb   # SmartCentres data collection
├── 02_yfinance_scraping.ipynb       # Stock-price and dividend data collection
├── 03_bank_of_canada_scraping.ipynb # Macroeconomic data collection
├── 04_wowa_scraping.ipynb           # Canadian REIT competitor data collection
├── 05_eda (2).ipynb                 # Exploratory data analysis and visualizations
├── data/                            # Collected CSV datasets
├── pdfs/                            # Annual reports and financial statements
└── screenshots/                     # Analysis visualizations used below
```

## Screenshots

### Market Capitalization
![Market capitalization analysis](screenshots/Marketcap.png)

### Stock Price Comparison
![Stock price comparison](<screenshots/shockprice comparision.png>)

### Dividend Yield Growth
![Dividend yield growth](<screenshots/Yeild growth.png>)

## Technologies
- Python 3
- Google Colab / Jupyter Notebook
- pandas, NumPy
- Matplotlib
- yfinance
- Bank of Canada Valet API

## Environment Setup

### Requirements
Install dependencies from `requirements.txt`:
```bash
pip install -r requirements.txt
```

Minimum required packages:
```
pandas
numpy
matplotlib
yfinance
```

### Data
The notebook expects source CSVs in a local `data/` folder, including:
- `yfinance_stock_prices.csv`
- `yfinance_company_profile.csv`
- `yfinance_dividends.csv`
- `smartcentres_financials_from_pdfs.csv`
- `smartcentres_properties.csv`
- `smartcentres_distributions.csv`
- `bank_of_canada_macro.csv`
- `wowa_competitors.csv`

These were collected separately from the public sources listed above and are provided in the `data/` folder of this repository.

## How to Run
1. Clone the repository:
   ```bash
   git clone https://github.com/<username>/8730-assignment.git
   cd 8730-assignment
   ```
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Open `05_eda (2).ipynb` in Jupyter Notebook, JupyterLab, or Google Colab.
4. Run all cells in order. The notebook loads the CSVs in `data/`, cleans and merges them, and generates the stock performance, dividend, occupancy, competitor, and macroeconomic visualizations used in the report.

## Analysis Summary
The notebook covers:
- Stock price trends, daily/monthly returns, and 50-day/200-day moving averages
- Dividend and distribution trends
- Occupancy rate and portfolio growth
- Financial ratios (debt-to-assets, FFO per unit)
- Competitor dividend yield comparison (Choice Properties, RioCan, Allied Properties, First Capital)
- Interest rate and macroeconomic context (Bank of Canada data)

## Use of Large Language Models (LLMs)
The workflow for data collection and analysis was as follows:
1. Relevant public data sources were identified manually (SmartCentres website, Bank of Canada, yfinance, WOWA, SEDAR+).
2. Google Gemini was used, within Google Colab, to generate the Python scraping code for each of these sources.
3. The generated code was run to collect and organize the data into the CSV files in `data/`.
4. The resulting datasets were cleaned and analyzed, and Gemini was used to assist in generating the Python chart/visualization code based on the cleaned data.
5. All generated code and outputs were reviewed, tested, and verified before inclusion, and the results were interpreted manually to form the final investment recommendation.

An LLM was also used to assist with structuring and formatting written documentation. LLMs were not used as a source of factual claims — all statistics and factual statements in the report are supported by cited sources. A full log of prompts used is included in `prompts_used.pdf`.

## License
This project was completed for academic purposes as part of BSMM-8730 at the University of Windsor.
