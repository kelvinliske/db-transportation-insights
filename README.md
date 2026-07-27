Markdown
# 🚆 German Transit Reliability vs. Municipal Accessibility Infrastructure

An end-to-end Data Science project analyzing the statistical relationship between regional train punctuality (*Deutsche Bahn*) and municipal disabled parking infrastructure across key cities in Schleswig-Holstein and Hamburg, utilizing open public data from **GovData.de**.

---

## 📌 Executive Summary

Urban mobility for individuals with reduced mobility depends on a seamless intermodal experience. This project combines transit reliability metrics with accessibility infrastructure data to evaluate whether cities with higher rail punctuality also provide stronger physical accessibility support.

---

## 🛠️ Data Architecture & Pipeline

           ┌───────────────────────┐
           │   GovData.de Portal   │
           └───────────┬───────────┘
                       │
         ┌─────────────┴─────────────┐
         ▼                           ▼
┌───────────────────┐       ┌───────────────────┐
│ DB Train Datasets │       │ Parking Facilities│
└─────────┬─────────┘       └─────────┬─────────┘
│                           │
▼                           ▼
Data Cleaning & Regex     Data Aggregation & Regex
City Normalization        Capacity Normalization
│                           │
└─────────────┬─────────────┘
│
▼
┌───────────────────────┐
│  df_insight (Merged)  │
└───────────┬───────────┘
│
▼
┌───────────────────────┐
│ Statistical Analysis  │
│  - Pearson (Linear)   │
│  - Spearman (Rank)    │
└───────────┬───────────┘
│
┌─────────────┴─────────────┐
▼                           ▼
┌─────────────────────────┐  ┌───────────────────────┐
│ correlation_analysis.png│  │ processed_data.csv    │
└─────────────────────────┘  └───────────────────────┘


---

## 📊 Key Findings & Visualizations

The correlation analysis compares the average rail punctuality percentage (`avg_punctuality_pct`) against total municipal disabled parking capacity (`total_disabled_parking_spaces`).

* **Pearson Correlation ($r$):** Evaluates linear association between punctuality and capacity.
* **Spearman Correlation ($\rho$):** Evaluates rank-order monotonic consistency among municipalities.

![Correlation Analysis](correlation_analysis.png)

---

## 📁 Repository Structure

```text
├── data/
│   ├── raw/                        # Raw downloads from GovData.de
│   └── processed_transport_accessibility.csv  # Final aggregated dataset
├── outputs/
│   └── correlation_analysis.png    # High-res correlation plot
├── pipeline.py                     # Modular ETL and analysis script
├── notebook.ipynb                 # Exploratory Data Analysis (EDA)
└── README.md                      # Documentation
🚀 How to Run
Clone the repository:

Bash
git clone [https://github.com/your-username/german-transit-accessibility.git](https://github.com/your-username/german-transit-accessibility.git)
cd german-transit-accessibility
Install dependencies:

Bash
pip install pandas numpy matplotlib seaborn scipy
Execute the automated pipeline:

Bash
python pipeline.py