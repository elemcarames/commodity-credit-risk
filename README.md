# Commodity Credit Risk Analysis

**Credit risk analysis for Brazilian agricultural commodities using real-world rural credit data.**

Built to demonstrate end-to-end data science applied to the financial sector —
from raw government data to predictive models and actionable insights.

---

## Business Questions

This project investigates the following questions using data from SICOR
(Sistema de Operações do Crédito Rural — Banco Central do Brasil):

1. **Risk by commodity** — Do coffee, sugarcane and orange have different credit risk profiles?
   Which has the highest historical default rate?

2. **Regional risk** — Which Brazilian states concentrate the highest credit risk per commodity?

3. **Financial anomalies** — Are there operations with atypical financial characteristics
   that may indicate guarantee overvaluation or data inconsistencies?

4. **Seasonality** — Does credit risk vary by harvest year?
   How do climate and market events reflect in the data?

5. **Default predictor profile** — Which operation characteristics
   (value, term, funding source, modality) are most predictive of default?

6. **Program impact** — Do government-backed operations carry different risk
   than market operations?

---

## Dataset

| Source | System | Coverage |
|---|---|---|
| Banco Central do Brasil | SICOR | 2018–2024 |

**Tables used:**
- `operacao` — 500,000 rural credit contracts (coffee, sugarcane, orange)
- `saldo` — 500,000 monthly balance records with operation status
- `empreendimento` — crop and financing details

**Key stats:**
- CAFÉ: 388,107 operations · avg ticket R$ 197k
- CANA-DE-AÇUCAR: 87,522 operations · avg ticket R$ 517k
- LARANJA: 24,371 operations · avg ticket R$ 313k
- Overall default rate: ~7.5% (including overdue, renegotiated, written-off)

> Raw data files are not included in this repository due to size constraints.
> Run `notebooks/01_data_ingestion.ipynb` to reproduce the local database.

---

## Project Structure

```bash
commodity-credit-risk/
│
├── notebooks/
│   ├── 01_data_ingestion.ipynb      # BigQuery → SQLite local database
│   ├── 02_eda_sql.ipynb             # Exploratory analysis in pure SQL
│   ├── 03_anomaly_detection.ipynb   # Anomaly detection pipeline
│   └── 04_credit_risk_model.ipynb  # Credit risk ML model
│
├── src/
│   ├── database.py                  # SQLite connection utilities
│   └── queries.py                   # Reusable SQL queries
│
├── data/                            # Local database (not versioned)
└── README.md
```

---

## Stack

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-4479A1?style=flat&logo=postgresql&logoColor=white)
![SQLite](https://img.shields.io/badge/SQLite-003B57?style=flat&logo=sqlite&logoColor=white)
![BigQuery](https://img.shields.io/badge/BigQuery-4285F4?style=flat&logo=google-cloud&logoColor=white)
![Scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat&logo=scikit-learn&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat&logo=pandas&logoColor=white)

---

## Getting Started

```bash
git clone https://github.com/elemcarames/commodity-credit-risk.git
cd commodity-credit-risk
python -m venv venv --system-site-packages
.\venv\Scripts\activate
pip install -r requirements.txt
```

Then run `notebooks/01_data_ingestion.ipynb` to build the local database.

---

## About

Built by [Elem Carames](https://github.com/elemcarames) — Data Scientist and PhD in Food Science,
applying rigorous analytical methodology to financial risk problems.

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=flat&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/elem-carames)