# 🇵🇰 Pakistan Socioeconomic Dashboard

> **DSC327 — Data Visualization Techniques | Lab Terminal Project | Spring 2026**
> **COMSATS University Islamabad | BDS 7 | Submission: 19 June 2026**

An interactive web-based data visualization system built with **D3.js v7** analyzing Pakistan's socioeconomic development across 5 domains, **565 data points**, **20+ visualizations**, and **12 interaction techniques** — covering 2000–2023.

---

## 🚀 Live Demo

**GitHub Pages:** `https://<your-username>.github.io/pakistan-dashboard/`

> Replace `<your-username>` with your actual GitHub username after deploying.

---

## 📁 Project Structure

```
pakistan-dashboard/
├── index.html                 ← Main application (single-file, all-in-one)
├── README.md                  ← This file
└── DSC327_Design_Report.docx  ← Design documentation report
```

---

## 🏃 How to Run Locally

```bash
# Option 1: Just open in browser (simplest)
open index.html

# Option 2: Local server (recommended — avoids CORS issues)
python -m http.server 8080
# → Visit http://localhost:8080
```

---

## 🌐 Deploy to GitHub Pages (Free Hosting)

### Option A — Upload via GitHub Website (No terminal needed)
1. Go to github.com → New repository → name it `pakistan-dashboard` → Public
2. Click **uploading an existing file** → drag `index.html` and `README.md`
3. Commit changes
4. Go to **Settings → Pages → Source: Deploy from branch → main / root**
5. Wait ~2 minutes → your site is live at `https://<username>.github.io/pakistan-dashboard/`

### Option B — Git command line
```bash
git init && git add . && git commit -m "Pakistan Socioeconomic Dashboard — DSC327"
git remote add origin https://github.com/<username>/pakistan-dashboard.git
git push -u origin main
# → Then: Settings → Pages → main branch → / (root)
```

---

## 🎮 Interactive Features (12 Techniques)

| # | Feature | Location | Description |
|---|---------|----------|-------------|
| 1 | **PKR ₨ / USD $ Toggle** | Header (global) | Converts ALL monetary values using historical exchange rates (₨52→₨283) |
| 2 | **Year Slider** | Overview + Population | Drag to any year — KPI cards, radar chart, and population pyramid animate live |
| 3 | **Time Range Filter** | Overview, Economy | All / 2000–2010 / 2010–2023 — filters all charts in the section |
| 4 | **Chart Type Switcher** | Economy | Bar ↔ Lollipop for GDP growth rate |
| 5 | **Sort Control** | Economy | By Year (chronological) vs By Value (ranked high→low) |
| 6 | **Legend Click Toggle** | Overview | Click any legend item to fade/restore that series |
| 7 | **Metric Selector** | Education | Literacy / Enrollment / Spending — swaps both charts |
| 8 | **View Selector** | Education | Trend (time series) vs Province (geographic comparison) |
| 9 | **Comparison Toggle** | Health | Pakistan vs South Asia average / Pakistan only |
| 10 | **Scatter Axis Selector** | EDA | 3 X-axis × 3 Y-axis = 9 combinations with live OLS regression |
| 11 | **Hover Tooltips** | All charts | Every data mark shows year, value, and context on hover |
| 12 | **Animated Entry** | All charts | Lines draw left-to-right, bars grow from baseline, bubbles expand |

---

## 📊 Chart Types Used (14 Types, 20+ Charts)

| Chart Type | Used In | Purpose |
|-----------|---------|---------|
| Line Chart | Overview, Economy, Education, Health | Temporal trends |
| Area Chart | Economy (inflation, GDP/cap), Health (mortality), Population (fertility) | Volume + trend |
| Stacked Area | Education (enrollment) | Multi-series with fill |
| Bar Chart | Economy (GDP growth), Education (gender gap) | Magnitude comparison |
| Lollipop Chart | Economy (GDP growth alt), Education (enrollment change, GPI) | Ink-efficient bar alternative |
| Radar / Spider | Overview | Multivariate profile comparison |
| Bubble Chart (4D) | Health | 4 variables: x, y, size, color |
| Donut Chart | Population | Part-to-whole proportion |
| Histogram | EDA | Distribution of GDP growth rates |
| Heatmap | EDA | 7×7 Pearson correlation matrix |
| Scatter + Regression | EDA, Education | Correlation with OLS line + r value |
| Slope Chart | EDA | Before/after (2000 → 2023) comparison |
| Grouped Horizontal Bar | Education | Provincial literacy by gender |
| Population Pyramid | Population | Age-sex structure (animated) |

---

## 📝 What Was Updated (v2 — 19 June 2026)

- ✅ **Legends added** to Life Expectancy chart (Pakistan / South Asia / Gap), Urban-Rural Donut, and Fertility Rate chart
- ✅ **Education secondary area** now populates with a dynamic insight box + color legend (6 different combinations from 2 controls)
- ✅ **Population insight box** added explaining demographic transition significance
- ✅ **Footer updated** with authors, submission date, and full data source list
- ✅ **Code documentation** added — full file-structure comment block at top of `<script>` with all 18 data variables source-attributed
- ✅ **Data array comments** — every variable in the D object has an inline `| Source:` annotation

---

## 💱 Currency Feature

Default: **PKR ₨** (Pakistani Rupee) with historical USD/PKR exchange rates per year (2000: ₨52 → 2023: ₨283 — a 5.4× depreciation).

Toggle to **USD $** for international comparison. All KPIs, axis labels, tooltips, and the data table update simultaneously via the `curVal(usdValue, yearIndex)` helper.

---

## 🗃️ Dataset: 565 Data Points

| Domain | Indicators | Points | Sources |
|--------|-----------|--------|---------|
| Economy | GDP, growth, inflation, exports, imports, per capita | 144 | World Bank, SBP |
| Education | Literacy (M/F/All), enrollment (3 levels), spending | 168 | UNESCO, PBS, UNICEF |
| Health | Life expectancy (PK + SA), mortality (infant + U5), health spending | 96 | WHO, World Bank |
| Population | Total, urban %, fertility, pyramid (16 age groups × 2 genders) | 114 | PBS, UN Population Division |
| Cross-domain | Pearson correlation matrix (7×7), provincial literacy (5 provinces × 2) | 43 | PBS, UNICEF |
| **Total** | **18 variables** | **565** | |

**Primary Sources:** World Bank · PBS · SBP · UNESCO · WHO · UNICEF

---

## 🔬 Key Findings

- **GDP grew 4.5×** over two decades but real per-capita income peaked in 2018 and has since declined
- **Gender literacy gap: 25 points** — unchanged for 23 years despite nominal gains
- **Literacy ↔ Life Expectancy: r = 0.98** — education is Pakistan's single highest-leverage development variable
- **2022–23 inflation at 29.2%** — highest in Pakistan's modern history, a 50-year record
- **Balochistan female literacy: 23%** vs ICT male literacy: 88% — a 65-point intra-country gap
- **Infant mortality fell 41%** (92 → 54.3 per 1,000) — the strongest health achievement of the period

---

## 🛠️ Tech Stack

| Tech | Version | Purpose |
|------|---------|---------|
| HTML5 + CSS3 | — | Structure, styling, CSS custom properties |
| JavaScript ES6+ | — | Logic, state management, interactivity |
| **D3.js** | **v7.8.5** | All 20+ visualizations |
| Google Fonts | — | Source Serif 4 (headings) + Outfit (body) |

**Zero build tools. Zero npm. Single HTML file. One CDN script tag.**

---

## 👥 Authors

| Name | Role |
|------|------|
| Sarwat | Visualization design, D3.js implementation, interactivity, code architecture |
| [Partner Name] | Data collection, EDA, preprocessing, design report writing |

**Course:** DSC327 — Data Visualization Techniques | **Instructor:** [Instructor Name]
**Program:** BDS 7 | **University:** COMSATS University Islamabad
**Submission:** 19 June 2026
