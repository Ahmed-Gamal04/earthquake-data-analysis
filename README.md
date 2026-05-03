# 🌍 Earthquake Data Analysis (1995–2023)
### Data Science Project | The British University in Egypt

[![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python)](https://www.python.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange?logo=jupyter)](https://jupyter.org/)
[![Dataset](https://img.shields.io/badge/Dataset-1000%20rows-green)]()

---

## 📌 Overview

A full exploratory data analysis (EDA) of global earthquake data spanning **1995 to 2023**. This project covers data cleaning, feature engineering, aggregations, binning, and **15+ visualizations** answering meaningful research questions about earthquake patterns, tsunami risk, alert distribution, and seismic monitoring quality.

This is a **two-phase project** — Phase 1 focused on cleaning and aggregation, Phase 2 introduced deeper analytical questions per team member.

---

## 👥 Team Members

| Name | Questions |
|---|---|
| Ahmed Gamal | Depth vs. tsunami probability, seismic monitoring quality, dmin vs. gap/nst, day vs. night detection, alert distribution |
| Ahmed Abousheisha | Depth/magnitude vs. human perception (CDI, MMI, SIG) by region |
| Karim | Magnitude vs. depth level, frequency of magnitude ranges, shallow earthquakes vs. damage |
| Mohamed Hisham | Earthquake trends over time, deaths vs. magnitude, regional death differences |

---

## 📁 Repository Structure

```
earthquake-analysis/
│
├── DataScienceProjectphase2_G24_Earthquake.ipynb   # Main analysis notebook
├── Earthquake1995.csv                               # Dataset
│
├── report/
│   └── G24_Earthquake_Report.pdf                   # Project report
│
├── presentation/
│   └── G24_Earthquake_Presentation.pptx            # Slides
│
├── README.md
└── requirements.txt
```

---

## 📊 Dataset

**File:** `Earthquake1995.csv`  
**Rows:** ~1,000 earthquakes  
**Period:** 1995–2023  
**Source:** USGS / publicly available earthquake catalog

**Key columns used:**

| Column | Description |
|---|---|
| `date_time` | Timestamp of the earthquake |
| `magnitude` | Richter scale magnitude |
| `depth` | Depth in km |
| `latitude`, `longitude` | Geographic coordinates |
| `location`, `country`, `continent` | Location info (cleaned + engineered) |
| `tsunami` | Whether a tsunami was triggered (0/1) |
| `alert` | Alert level issued |
| `cdi`, `mmi`, `sig` | Human perception intensity metrics |
| `nst`, `gap`, `dmin` | Seismic monitoring quality indicators |

---

## 🧹 Data Cleaning Steps

- Dropped unused column (`net`)
- Filled null `location` values using **reverse geocoding** (`geopy`)
- Extracted and cleaned `country` from location strings
- Mapped countries to **continents** using `pycountry-convert`
- Filled missing `alert` values with `"No Warning Issued"`
- Converted `date_time` to datetime format
- Applied **Label Encoding** on the `alert` column
- Engineered new columns: `year`, `continent`, `depth_category`, `mag_bin`, `time_period`

---

## 🔬 Research Questions Answered

### Phase 1
- Which continents have the highest average earthquake magnitude?
- Which regions are most at risk of tsunamis?
- What alert levels correspond to tsunami-causing earthquakes?
- What are the top 10 countries by earthquake frequency?

### Phase 2 — Ahmed Gamal
1. Does earthquake **depth** affect tsunami probability across regions?
2. Does better **seismic monitoring** (high NST, low GAP) detect higher or lower magnitude quakes?
3. How does **distance to nearest station (dmin)** affect gap and NST?
4. Do **night earthquakes** differ in magnitude or detection quality from daytime ones?
5. What is the **distribution of alert levels**?

### Phase 2 — Ahmed Abousheisha
1. What degree of correlation do depth/magnitude yield versus human perception (CDI, MMI, SIG) by region?

### Phase 2 — Karim
1. How does magnitude vary across **depth levels**?
2. Which **magnitude range** occurs most frequently?
3. Do **shallow earthquakes** produce higher damage (CDI)?

---

## 🛠️ Tech Stack

```
pandas        — Data manipulation
numpy         — Numerical operations
matplotlib    — Plotting
seaborn       — Statistical visualizations
sklearn       — Label encoding
geopy         — Reverse geocoding
pycountry     — Country lookup
pycountry-convert — Country → continent mapping
```

---

## ▶️ How to Run

1. **Clone the repository**
   ```bash
   git clone https://github.com/YOUR_USERNAME/earthquake-analysis.git
   cd earthquake-analysis
   ```

2. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

3. **Launch the notebook**
   ```bash
   jupyter notebook DataScienceProjectphase2_G24_Earthquake.ipynb
   ```

> ⚠️ Make sure `Earthquake1995.csv` is in the same directory as the notebook before running.

---

## 📄 Report & Presentation

The `report/` and `presentation/` folders contain the written report and slide deck submitted as part of the course deliverables.

---

## 📜 License

This project was completed for academic purposes at **The British University in Egypt**.  
Not intended for commercial use.
