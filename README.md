![Project Thumbnail](dashboard/personal_health_activity_dashboard.png)

# Personal-Health-Activity-Apple-watch
### A Databricks Time‑Series Analysis of Apple Health Data (2018–2025)

##  Table of Contents
- Overview
- Project Structure
- Tools & Technologies
- Dashboard Visualizations
- Key Insights
- Requirements
- How to Reproduce This Project
- Future Enhancements
- Why This Project Matters
- Author


##  Overview
This project explores seven years of personal Apple Health data using Databricks, PySpark, and SQL. The goal was to build a reproducible data pipeline and an interactive dashboard that reveals long‑term patterns in physical activity and cardiovascular behavior.

The project demonstrates:
- Data extraction from Apple Health XML exports  
- Cleaning and normalization of irregular time‑series data  
- Transformation into Delta tables using PySpark  
- Analytical queries using Databricks SQL  
- Dashboard creation for trend analysis and insight generation  

---


##  Project Structure


/notebooks
    ├── 01_parse_apple_health_xml.ipynb
    ├── 02_transform_activity_tables.ipynb
    ├── 03_feature_engineering.ipynb

/dashboard
    ├── personal_health_activity_dashboard.png

/data
    ├── sample_apple_health_export.xml
    ├── processed/
        ├── heart_rate_delta/
        ├── walking_delta/
        ├── cycling_delta/

README.md

---


This structure highlights:
- **ETL pipeline notebooks**  
- **Dashboard assets**  
- **Raw and processed data**  
- **A clean, reproducible layout**  

---



###  Cardiovascular Trends
- Average daily heart rate shows a gradual downward trend from 2020–2024, suggesting improved cardiovascular efficiency.
- Higher cycling distances correlate with higher heart‑rate ranges, indicating increased training intensity on long‑ride days.

###  Walking Behavior
- Walking distance shows strong seasonality: consistent summer peaks and winter declines.
- Despite seasonal variation, overall walking volume remains stable year‑to‑year.

###  Cycling Activity
- Cycling volume increased significantly after 2021, reflecting a shift in training habits.
- Long‑term cycling distance shows habit formation: more frequent rides and longer average distances.

###  Data Quality Observations
- Apple Health XML exports contain irregular timestamps and nested attributes, requiring careful parsing.
- Missing or inconsistent entries highlight the importance of robust cleaning and normalization steps.

##  Tools & Technologies
- **Databricks** (SQL, Delta Lake, Dashboards)
- **PySpark** for ETL and time‑series transformations
- **Python** for XML parsing and feature engineering
- **Apple Health** data export (XML)
- **SQL** for aggregations and trend analysis

---

##  Dashboard Visualizations
![alt text](image-1.png)
The dashboard includes four core analyses:

### **1. Heart Rate vs. Distance Cycled**
A scatter plot showing how heart rate intensity changes with cycling distance.  
Useful for understanding training load and cardiovascular response.

### **2. Daily Average Heart Rate**
A long‑term trend line (2020–2024) showing changes in resting and active heart rate over time.

### **3. Daily Walking Distance**
A multi‑year time‑series showing walking volume, seasonality, and habit consistency.

### **4. Daily Cycling Distance**
A trend line showing cycling activity growth from 2021–2023.

---

##  Key Insights
- **Cycling volume increased significantly after 2021**, with clear peaks during summer months.  
- **Walking distance shows strong seasonality**, with winter dips and summer highs.  
- **Average daily heart rate gradually decreased over several years**, suggesting improved cardiovascular efficiency.  
- **Higher cycling distances correlate with higher heart‑rate ranges**, indicating increased training intensity.

##  Requirements

To run or reproduce this project, you will need:

- **Python 3.10+**
- **Databricks Workspace** (Community Edition or Enterprise)
- **PySpark**
- **Databricks SQL** enabled
- Ability to export **Apple Health data** from an iPhone (XML format)

##  How to Reproduce This Project

Follow these steps to recreate the full pipeline and dashboard:

1. **Export Apple Health Data**
   - On your iPhone: Health App → Profile → *Export All Data*
   - This produces a large XML file.

2. **Upload the XML to Databricks**
   - Use Databricks FileStore or DBFS to upload the exported XML file.

3. **Run Notebook 01 — XML Parsing**
   - `01_parse_apple_health_xml.ipynb`
   - Parses the Apple Health XML into structured PySpark DataFrames.

4. **Run Notebook 02 — Transform Activity Tables**
   - `02_transform_activity_tables.ipynb`
   - Cleans, normalizes, and writes Delta tables for:
     - Heart rate  
     - Walking  
     - Cycling  

5. **Run Notebook 03 — Feature Engineering**
   - `03_feature_engineering.ipynb`
   - Adds time‑series features and prepares tables for visualization.

6. **Build or Import the Dashboard**
   - Use Databricks SQL to recreate the four visualizations.
   - Or import the provided dashboard screenshot as reference.

7. **Explore Insights**
   - Use the dashboard to analyze long‑term trends in heart rate, walking, and cycling activity.

---

##  Future Enhancements

- **Activity Clustering:** Group workouts by heart‑rate intensity using k‑means or hierarchical clustering.
- **Forecasting Models:** Predict future walking or cycling distance using Prophet or ARIMA.
- **Anomaly Detection:** Identify unusually high or low heart‑rate days using statistical thresholds or isolation forests.
- **Sleep & Recovery Integration:** Add sleep, HRV, and resting heart‑rate metrics for a more holistic health profile.
- **Power BI / Tableau Version:** Build a cross‑platform dashboard for broader accessibility.
- **Automated Pipeline:** Use Databricks Jobs to schedule daily or weekly ingestion of new Apple Health exports.

##  Why This Project Matters
This project demonstrates how personal health data can be transformed into meaningful long‑term behavioral insights using modern data engineering tools. It blends technical rigor (ETL, PySpark, Databricks SQL) with human‑centered analysis, showing how data can reveal patterns in habit formation, cardiovascular trends, and lifestyle changes over time.


## 📎 Author
**Toba Olorunsogo**  
Data Scientist & Communications Specialist  
Winnipeg, MB  
