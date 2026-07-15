# Deutsche Bahn (DB) & German Transportation Insights 🇩🇪

This project focuses on analyzing logistics, accessibility, and train punctuality data from Germany's transportation ecosystem.

## Current Progress
- **Environment Setup:** Configured VS Code with Python, Pandas, and Jupyter Notebook.
- **Data Cleaning:** Explored the `behindertenparken.csv` dataset (1,874 rows). 
- **Key Insight:** Identified that the largest accessibility parking hubs in the dataset belong to major infrastructure networks like the Allianz Arena (Munich) and Berlin Airport (BER), rather than local train stations.
- **Data Quality:** Handled missing values (`NaN`) in columns like `type` and `operator_name` using Pandas to ensure clean data for future BI dashboards.

## Next Steps
- Implement data transformation for the train punctuality dataset (`puenktlichkeit`).
- Create an interactive geo-spatial dashboard using Google Looker Studio.
