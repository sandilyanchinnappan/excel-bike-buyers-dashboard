# Excel Data Analytics Dashboard - Bike Buyers Dataset

## 📌 Project Overview
This project is a complete, end-to-end Excel analytics build covering data cleaning, pivot table analysis, chart creation, and interactive dashboard design using a **Bike Buyers dataset** (customer demographics, income, commute distance, age, and purchase status).

The goal is to take a raw, messy dataset and transform it into a fully interactive business dashboard — demonstrating not just cleaning skills, but the ability to derive insights and present them visually for decision-making.

---

## 🖼️ Dashboard Preview
![Bike Sales Dashboard](screenshots/dashboard_preview.png)

---

## 🏗️ Workbook Structure
The project is organized into four distinct tabs:
1. **Raw Data** – Untouched original dataset.
2. **Working Sheet** – Active copy used for cleaning and transformation.
3. **Pivot Table** – Sheet housing all underlying calculations and pivot tables.
4. **Dashboard** – Clean canvas for the final interactive visual layout.

---

## 🧹 Data Cleaning & Transformation

### 1. Remove Duplicates
- Used **Data → Remove Duplicates** on the Working Sheet to drop identical rows.

### 2. Standardize Text Fields (Find & Replace)
- **Marital Status:** Replaced `M` with `Married` and `S` with `Single` using `Ctrl + H`.
- **Gender:** Replaced `M` with `Male` and `F` with `Female` using `Ctrl + H`.

### 3. Formatting Currency
- Ensured the `Income` column was consistently formatted as **Currency**.

### 4. Creating Age Buckets (Nested IF Statement)
Individual ages (25–89) created noisy charts, so ages were grouped into brackets using a nested `IF` formula:
```excel
=IF(L2>54, "Old", IF(L2>=31, "Middle Age", IF(L2<31, "Adolescent", "Invalid")))
```
- **Adolescent:** ≤ 30 years old
- **Middle Age:** 31–54 years old
- **Old:** 55+ years old

---

## 📊 Pivot Tables & Charts

### Chart 1: Average Income per Purchase by Gender
- **Rows:** `Gender` (Male, Female)
- **Columns:** `Purchased Bike` (No, Yes)
- **Values:** Average of `Income` (formatted as whole numbers with currency/commas)
- **Visualization:** Clustered Column Chart
- **Insight:** Individuals who bought a bike had a higher average income than non-buyers across both genders.

### Chart 2: Customer Commute Distance
- **Rows:** `Commute Distance`
- **Columns:** `Purchased Bike` (No, Yes)
- **Values:** Count of `Purchased Bike`
- **Data Cleaning Note:** Standardized inconsistent labels (e.g., `10+ Miles` → `More than 10 Miles`) so distances sort logically from `0-1 Miles` to `More than 10 Miles`.
- **Visualization:** Clustered Bar/Column Chart

### Chart 3: Customer Age Brackets
- **Rows:** `Age Brackets` (Adolescent, Middle Age, Old)
- **Columns:** `Purchased Bike` (No, Yes)
- **Values:** Count of `Purchased Bike`
- **Visualization:** Line Chart with Markers
- **Insight:** Middle-aged customers (31–54) purchase bikes at significantly higher rates than younger or older demographics.

---

## 🖥️ Dashboard Design & Interactivity

### Clean Canvas Preparation
- Turned off gridlines (**View → uncheck Gridlines**).
- Inserted a merged title header block labeled **"Bike Sales Dashboard"**.

### Layout Strategy
- Copied chart visuals from the Pivot Table sheet onto the Dashboard.
- Aligned and evenly spaced charts using **Shape Format → Align** tools.

### Interactive Slicers
- Added slicers via **PivotChart Analyze → Insert Slicer** for:
  - Marital Status
  - Region
  - Education
- Connected all slicers to every relevant pivot table via **Report Connections**, turning the dashboard into a fully interactive filtering experience.

---

## 💡 Key Takeaway
Connecting slicers to all underlying pivot tables transforms a static set of Excel charts into a fully interactive business dashboard — enabling dynamic, on-the-fly filtering by demographic and behavioral segments.
