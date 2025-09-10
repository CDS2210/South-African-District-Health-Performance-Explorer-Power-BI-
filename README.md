# South African District Health Performance Explorer (Power BI)

**An interactive Power BI report that tracks district-level health system performance and disease surveillance in South Africa.**  
It benchmarks provinces/districts, normalises by population, and highlights outliers over time.

![Overview Page](docs/screenshots/Overview.png)

---

## ✨ Highlights
- National overview KPIs (PHC headcount per capita, antenatal visit <20w, facility deliveries, TB success).
- District benchmarking with “% vs national” and performance bands.
- Disease surveillance trends (notifiable conditions) with YoY change and alerting.
- Interactive map (Province → District drilldown) and tooltip scorecards.
- Lightweight repo: template `.pbit` + small sample CSVs so it opens instantly.

---

## 📁 Repo Structure

docs/ # screenshots & data dictionary
data_raw/ # tiny sample inputs (real sources linked below)
data_model/ # cleaned model CSVs used by the .pbit
powerbi/ # Power BI template + theme

---

## 🧰 Getting Started
1. Open **powerbi/SA_Health_Explorer.pbit** in Power BI Desktop.
2. When prompted, choose the local folder for `data_model/`.
3. Hit **Refresh**. The template loads the sample CSVs (added in Step 2).

> If you see field warnings, it just means the sample data isn’t there yet — continue to **Step 2** of this guide (to be added).

---

## 🗂️ Data Sources (links added in Step 2)
- District Health Barometer (latest)
- Stats SA Mid-Year Population Estimates (latest)
- NICD Notifiable Medical Conditions monthly reports
- Optional facility locations (for map tooltips/nearest-facility demo)

*Note:* This project uses public, aggregate data. No personal/identifiable information is included.

---

## 🧱 Data Model (star-ish)
**Facts:** `Fact_DHB`, `Fact_NMC`, `Fact_Pop`  
**Dimensions:** `Dim_Geography`, `Dim_Time`, `Dim_Indicator`, `Dim_Condition`

A small, ready-to-run sample will ship in **Step 2**.

---

## 📊 Pages
1) Overview • 2) Benchmark • 3) Disease • 4) Map • 5) Equity & Spend • 6) About (definitions & sources)

---

## 🔒 Production Considerations (for interviews)
- Scheduled refresh with parameters for year/URL.
- Row-Level Security (RLS) by province/district.
- Data quality panel (late/missing months).
- Facility-level layers where permitted; always aggregate & de-identify.

---

## 🗺️ Roadmap
- [ ] Add sample data CSVs (Step 2)
- [ ] Publish `.pbit` with Power Query steps
- [ ] Add screenshots & short demo GIF
- [ ] Optional Deneb visuals (boxplot) for distribution view

---

📊 **Overview**
This Power BI project explores district health indicators and notifiable medical conditions in South Africa.  
It uses sample data from DHB, Stats SA and NICD (2024 demo).  

⚙️ **Features**
- National average vs district performance (±5% threshold)
- Best and worst performing districts
- District comparison with conditional color bands
- Map of district performance by indicator
- Notifiable Medical Conditions per 100k (Measles, Shigellosis)
- Dynamic slicers (Year, Province, Indicator)

📂 **Project structure**
- `data_model/` – sample CSV data (dimensions + facts)
- `powerbi/SA_Health_Dashboard.pbit` – Power BI template
- `docs/screenshots/` – dashboard visuals

🚀 **How to run**
1. Clone the repo  
2. Open `powerbi/SA_Health_Dashboard.pbit` in Power BI Desktop  
3. Point to the CSV files in `data_model/` when prompted  

💡 **Note:** All data is illustrative demo only, not official health data.

---
## 🤝 License
MIT — see [LICENSE](LICENSE).
