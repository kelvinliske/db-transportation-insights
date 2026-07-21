# 🚆 German Transport & Municipal Accessibility Analysis

An end-to-end data integration and analysis project evaluating the relationship between regional train punctuality (**Deutsche Bahn**) and municipal accessible parking infrastructure in Germany.

---

## 📌 Project Overview
This project explores whether cities experiencing lower public transport reliability compensate with stronger municipal accessibility infrastructure (disabled parking spaces), or if infrastructural gaps exist simultaneously in both public transit and accessibility provisions.

---

## 📊 Data Sources

The datasets used in this project were retrieved directly from the official German Open Data Portal:

* **Portal:** [GovData — Das Datenportal für Deutschland](https://www.govdata.de/)
  1. **DB Transport Punctuality (`puenktlichkeit.csv`):** Historical punctuality levels (`puenktlichkeitsniveau_an`) for regional train lines across Germany (2010–2022).
  2. **Accessible Parking Infrastructure (`behindertenparken.csv`):** Spatial and municipal data on disabled parking spaces (`behindertenparken`), including capacity and location details.

---

## 🛠️ Data Pipeline & Methodology
- **Data Cleaning & Standardization:** Handled missing values, standardized city naming conventions, and cleaned numeric formats.
- **Pattern Matching Merge:** Developed a keyword extraction algorithm (`re.escape` string matching) to link train line route destinations (`linie`) with specific municipality records (`city`).
- **Data Aggregation:** Computed average punctuality rates per city against total accessibility capacities and parking facility counts.

---

## 📈 Key Findings (Work in Progress)
* **High Efficiency Corridors:** Cities like **Elmshorn** demonstrate high rail punctuality (~99.09%).
* **Major Transit Hubs:** Metropolitan hubs like **Hamburg** centralize accessibility capacity (220+ registered disabled parking spaces) while maintaining moderate punctuality levels (~88.48%).
* **Identified Gaps:** Outlying regional destinations like **Flensburg** show opportunities for both transit reliability improvement (~86.59%) and accessibility footprint expansion.

---

## 🚀 Next Steps
- [x] Data Collection & Cleaning
- [x] Cross-Dataset Matching Algorithm
- [ ] Statistical Correlation Analysis (Pearson / Spearman)
- [ ] Data Visualizations (Seaborn / Matplotlib)
- [ ] Business Insights & Executive Summary