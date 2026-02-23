# 📊 Power BI Dashboard Analytics

> A chart without context is just noise. A dashboard with the right KPIs is a compass.

A complete **business intelligence solution** combining Python-based exploratory data analysis with interactive **Power BI dashboards** for operational performance monitoring. Built for data-driven decision making.

---

## 📈 Dashboards Included

| Dashboard | Description |
|---|---|
| **Operations Overview** | Real-time KPI tracking — throughput, efficiency, SLA compliance |
| **Anomaly Monitoring** | Flagged outliers and trend deviations visualized over time |
| **Resource Utilization** | Equipment and workforce usage by site, shift and category |
| **Executive Summary** | High-level monthly reporting with drill-through capability |

---

## 🗂️ Project Structure

```
powerbi-dashboard-analytics/
│
├── data/
│   ├── raw/                      # Source CSV / Excel files
│   └── processed/                # Cleaned data ready for Power BI
│
├── python/
│   ├── eda.ipynb                 # Exploratory Data Analysis notebook
│   ├── preprocessing.py          # Data cleaning & feature engineering
│   └── export_to_csv.py          # Export processed data for Power BI
│
├── sql/
│   ├── kpi_queries.sql           # Core KPI SQL queries
│   └── aggregations.sql          # Pre-aggregated views for performance
│
├── powerbi/
│   └── dashboard.pbix            # Power BI Desktop file
│
├── requirements.txt
└── README.md
```

---

## ⚙️ Quickstart

**Python preprocessing:**
```bash
pip install -r requirements.txt
python python/preprocessing.py
```

**Power BI:**
1. Open `powerbi/dashboard.pbix` in Power BI Desktop
2. Update the data source path to point to `data/processed/`
3. Click **Refresh** — all visuals update automatically

---

## 🔢 KPIs Tracked

- ✅ Availability Rate (%)
- ✅ Mean Time Between Failures (MTBF)
- ✅ On-Time Delivery Rate
- ✅ Anomaly Frequency by Site
- ✅ Monthly Cost vs Budget Variance
- ✅ Resource Utilization Rate (%)

---

## 🎨 DAX Highlights

```dax
-- Availability Rate
Availability Rate =
DIVIDE(
    SUMX(Interventions, Interventions[Uptime_Hours]),
    SUMX(Interventions, Interventions[Total_Hours])
) * 100

-- Rolling 30-day anomaly count
Anomalies_30d =
CALCULATE(
    COUNT(Events[anomaly_flag]),
    DATESINPERIOD(Calendar[Date], LASTDATE(Calendar[Date]), -30, DAY),
    Events[anomaly_flag] = 1
)
```

---

## 📦 Tech Stack

- **Python 3.11** — EDA & preprocessing
- **Pandas / Matplotlib / Seaborn** — data exploration
- **SQL Server** — data source
- **Power BI Desktop** — dashboards & DAX
- **DAX** — calculated measures and KPIs

---

## 👤 Author

**ELOUAFI Abderrahmane**  
Ingénieur Big Data & Cloud — ENSET Mohammedia  
[LinkedIn](https://www.linkedin.com/in/abderrahmane-elouafi-43226736b/) • [Portfolio](https://my-first-porfolio-six.vercel.app/)
