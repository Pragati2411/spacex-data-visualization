# 🚀 SpaceX Falcon 9 — EDA with Data Visualization & Feature Engineering

![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-lightgrey?logo=pandas)
![Matplotlib](https://img.shields.io/badge/Matplotlib-Visualization-orange)
![Seaborn](https://img.shields.io/badge/Seaborn-Statistical%20Plots-teal)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

---

## 📌 Project Overview

This project performs **deeper Exploratory Data Analysis (EDA) and Feature Engineering** on the SpaceX Falcon 9 launch dataset, building on the initial EDA. The goal is to visualise relationships between launch parameters and landing outcomes, then prepare the data for machine learning by encoding categorical variables and converting all features to numeric form.

---

## 🎯 Objectives

- Perform Exploratory Data Analysis using Pandas and Matplotlib/Seaborn
- Visualise relationships between flight number, payload, orbit, and launch site
- Identify which launch sites and orbit types have the highest success rates
- Analyse the yearly trend in landing success
- Engineer features and apply one-hot encoding to categorical columns
- Prepare a fully numeric (`float64`) dataset ready for machine learning

---

## 🛠️ Tools & Libraries

| Tool | Purpose |
|------|---------|
| Python | Core programming language |
| Pandas | Data loading, cleaning, and manipulation |
| NumPy | Numerical operations |
| Matplotlib | Base visualisations |
| Seaborn | Statistical visualisations (catplot, barplot, lineplot) |
| Jupyter Notebook | Interactive analysis environment |

---

## 🔍 Key Analysis & Findings

### Task 1: Flight Number vs. Launch Site
- Visualised how launch frequency and success are distributed across launch sites
- **CCAFS LC-40** had a success rate of ~60%, while **KSC LC-39A** and **VAFB SLC-4E** had success rates of ~77%

### Task 2: Payload Mass vs. Launch Site
- Observed that **VAFB SLC-4E** has no rockets launched for heavy payloads (>10,000 kg)
- Heavier payloads are concentrated at CCAFS LC-40

### Task 3: Success Rate by Orbit Type
- Created a bar chart of success rate per orbit type
- **ES-L1, GEO, HEO, SSO, and VLEO** orbits show a 100% success rate
- **GTO, ISS, LEO, MEO, and PO** show more mixed/moderate success rates

### Task 4: Flight Number vs. Orbit Type
- In the **LEO** orbit, success appears related to flight number (later flights succeed more)
- In the **GTO** orbit, there's no clear relationship between flight number and success

### Task 5: Payload vs. Orbit Type
- Heavy payloads have higher success rates for **Polar, LEO, and ISS** orbits
- For **GTO**, both successful and unsuccessful landings occur across payload ranges, making it hard to distinguish a pattern

### Task 6: Yearly Success Trend
- Plotted a line chart of average success rate by year
- Success rate was 0% before 2013, then **steadily increased from 2013 to 2020**

---

## ⚙️ Feature Engineering

### Task 7: One-Hot Encoding
- Selected key features: `FlightNumber`, `PayloadMass`, `Orbit`, `LaunchSite`, `Flights`, `GridFins`, `Reused`, `Legs`, `LandingPad`, `Block`, `ReusedCount`, `Serial`
- Applied `pd.get_dummies()` to encode categorical columns: `Orbit`, `LaunchSite`, `LandingPad`, `Serial`
- Result: an 80-column fully encoded feature set

### Task 8: Type Casting
- Cast the entire `features_one_hot` dataframe to `float64` using `.astype(float)`
- Final dataset: **90 rows × 80 columns**, fully numeric and ready for machine learning

---

## 📁 Project Structure

```
spacex-data-visualization/
├── EDA with Data Visualization.ipynb   # Full EDA, visualisations & feature engineering
└── README.md                           # Project documentation (this file)
```

---

## ▶️ How to Run

1. **Clone the repository**
   ```bash
   git clone https://github.com/Pragati2411/spacex-data-visualization.git
   cd spacex-data-visualization
   ```

2. **Install dependencies**
   ```bash
   pip install pandas numpy matplotlib seaborn jupyter
   ```

3. **Launch Jupyter Notebook**
   ```bash
   jupyter notebook "EDA with Data Visualization.ipynb"
   ```

---

## 💡 Insights Summary

> Launch site, payload mass, orbit type, and flight number all influence Falcon 9 landing success. Success rates have improved steadily since 2013, and orbits like ES-L1, GEO, HEO, SSO, and VLEO show consistently perfect landing records. The engineered, fully numeric dataset (90 rows × 80 columns) is ready to serve as input for predictive machine learning models.

---

## 🔗 Related Projects in This Series

| Project | Description |
|--------|-------------|
| space-falcon-eda | Initial EDA & data wrangling on SpaceX launch data |
| EDA with SQL | Querying launch data using SQL for structured insights |
| ML — Loan Prediction | Classification model using Scikit-learn |

---

## 👩‍💻 Author

**Pragati Mistry** — Data Analyst | MSc Mathematics | IBM Data Science Professional Certificate  
📍 Surat, India | Open to Remote & Relocating to Mumbai / Hyderabad / Bangalore  
🔗 [GitHub Profile](https://github.com/Pragati2411)
