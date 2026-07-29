# 📉 Unemployment Analysis with Python

An end-to-end data analysis project examining unemployment trends across Indian states before and after the COVID-19 lockdown — built as **Task 2** of the CodeAlpha Data Science Internship.

The project goes beyond a notebook: it ships with a fully interactive, scrollable **data report** — *"Unemployment in India, read as a chart"* — combining narrative, live charts, a region × month heatmap, and a tuned regression model, all in a single self-contained HTML page.

---

## 🔴 Live Demo

**[Unemployment in India — Data Report](./index.html)**

Open `index.html` in any browser — no server, no dependencies. All charts render live via Chart.js from embedded data.

---

## 🧠 Project Overview

The goal is to analyze unemployment rate data across Indian regions, understand the impact of COVID-19, uncover seasonal/regional patterns, and translate the findings into insights that could inform economic or social policy.

**Workflow:**
1. **Data Cleaning & Exploration** — parsed and cleaned the regional unemployment dataset (28 regions, 14-month window spanning 2019–2020).
2. **Trend Analysis** — plotted the national unemployment rate over time, with a rural vs. urban toggle to compare trajectories.
3. **COVID-19 Impact Study** — split the dataset at the 25 March 2020 lockdown date and compared pre-lockdown vs. lockdown-and-after averages to isolate the shock.
4. **Regional & Seasonal Patterns** — built a region × month heatmap, ranked regions and zones by average unemployment, and identified a mild seasonal rhythm tied to agricultural/job cycles.
5. **Predictive Modeling** — trained and compared **six regression models** on region, area, labour participation rate, employment count, time, and an explicit lockdown flag; the best model was further tuned with **GridSearchCV**.
6. **Insight Generation** — surfaced feature importances driving the prediction and distilled the findings into policy-relevant notes.

---

## ✨ Features

- 📊 **Interactive trend chart** — toggle between overall / rural / urban unemployment series
- 🦠 **COVID-19 shock split** — side-by-side pre-lockdown vs. lockdown-and-after averages with % increase
- 🗺️ **Region × month heatmap** — color-coded unemployment intensity across all 28 regions over the full time window, with hover tooltips
- 🏆 **Hardest-hit regions** chart during lockdown & after
- 🧭 **Region & zone breakdowns** — sortable top-N view by average rate, plus zone-level comparison
- 📅 **Seasonality chart** — month-over-month rate pattern
- 🤖 **Sortable model comparison table** — RMSE, MAE, and R² across all six trained models, best model auto-highlighted
- 🔍 **Feature importance chart** for the final tuned model
- 📱 Scroll-reveal animations, sticky nav with scroll progress bar, fully responsive dark editorial layout

---

## 🗂️ Project Structure

```
Unemployment-Analysis-CodeAlpha/
├── Unemployment_in_India.csv         # Dataset: region, date, area, unemployment rate, labour participation, employment
├── Unemployment_Analysis.ipynb       # Full analysis: EDA, COVID-19 split, seasonality, modeling
├── index.html                        # Interactive scrollable data report
└── README.md
```

---

## 📊 Dataset

The dataset covers monthly unemployment statistics across Indian states/UTs:

| Column | Description |
|---|---|
| `Region` | State / Union Territory |
| `Date` | Observation month |
| `Area` | Rural / Urban |
| `Estimated Unemployment Rate (%)` | Target variable |
| `Estimated Labour Participation Rate (%)` | Share of population in the labour force |
| `Estimated Employed` | Number of people employed |

---

## 🛠️ Tech Stack

| Category | Tools |
|---|---|
| Language | Python |
| Data Handling | Pandas, NumPy |
| Visualization (notebook) | Matplotlib, Seaborn |
| Modeling | Scikit-learn (6 regression models + GridSearchCV tuning) |
| Environment | Jupyter Notebook |
| Report / Dashboard | HTML, CSS, Chart.js |

---

## 🤖 Modeling

Six regression models were trained on region, area, labour participation, employment count, time, and an explicit lockdown flag:

- Compared side-by-side on **RMSE**, **MAE**, and **R²**
- Best-performing model selected and further tuned via **GridSearchCV**
- Feature importance extracted from the final tuned model to identify the strongest drivers of the unemployment rate prediction

Exact scores for each model are available in the sortable comparison table inside the report (`index.html`) and in the notebook.

---

## 🚀 Getting Started

### Run the notebook
```bash
git clone https://github.com/<your-username>/Unemployment-Analysis-CodeAlpha.git
cd Unemployment-Analysis-CodeAlpha
pip install pandas numpy scikit-learn matplotlib seaborn jupyter
jupyter notebook Unemployment_Analysis.ipynb
```

### View the report
No setup required — just open `index.html` directly in your browser, or serve it locally:
```bash
python -m http.server 8000
# then visit http://localhost:8000/index.html
```

---

## 📈 Key Insights

- National unemployment held in a narrow band through most of 2019, then broke sharply upward in **April 2020**, coinciding with the nationwide lockdown.
- The **pre-lockdown vs. lockdown-and-after** split quantifies exactly how much of the overall average is attributable to the COVID-19 shock alone.
- Unemployment carries a distinct **regional geography** — some states/zones consistently run far hotter than the national average — plus a mild **seasonal rhythm** tied to agricultural and job cycles, independent of the pandemic.
- The lockdown flag and labour participation rate emerge as strong predictors, useful for **targeted, region-specific policy intervention** rather than a one-size-fits-all response.

---

## 🙌 Acknowledgements

Built as part of the **[CodeAlpha](https://www.codealpha.tech/)** Data Science Internship — Task 2: Unemployment Analysis with Python.

---

## 👩‍💻 Author

**Akanksha Singh** - https://www.linkedin.com/in/akanksha-singh-4715a0351/ 
© 2026

Video of the project : https://www.linkedin.com/feed/update/urn:li:ugcPost:7488284826911797250/


---
## 📄 License

This project is open source and available under the [MIT License](LICENSE).
