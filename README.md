# Healthcare Data Cleaning & Exploratory Data Analysis (Python)

**Author:** Parv Jain
- GitHub: [parvjain921](https://github.com/parvjain921)
- LinkedIn: [Parv Jain](https://www.linkedin.com/in/parv-jain-6b3038419)

## 🔴 Live Dashboard
**[View the interactive dashboard →](https://parvjain921.github.io/Healthcare-Data-Cleaning-Exploratory-Data-Analysis-Python-/)**
*(Replace this link with your actual repo name once uploaded — GitHub Pages URL follows the pattern `https://parvjain921.github.io/<repo-name>/`)*

A fully interactive, self-contained analytics dashboard built with vanilla JavaScript and hand-drawn SVG charts — no chart libraries, no external dependencies. Click through departments to see admissions, average stay, and billing update live.

## Overview
This project involves cleaning a messy, real-world-style healthcare admissions dataset and performing exploratory data analysis (EDA) and visualization using Python. The goal was to take raw, inconsistent hospital records and turn them into an analysis-ready dataset, then extract meaningful operational and financial insights from it — and present those insights as an interactive dashboard.

## Dataset
`healthcare_dataset_raw.csv` — ~151,800 patient admission records containing:

`PatientID`, `Name`, `Age`, `Gender`, `City`, `Diagnosis`, `Department`, `AdmissionDate`, `DischargeDate`, `BillingAmount`, `InsuranceProvider`, `DoctorName`

The raw data included inconsistent text casing, spelling variants, invalid ages, malformed dates, currency-formatted billing values, and missing/placeholder entries — typical of real hospital record systems.

## Project Workflow

### 1. Data Understanding
- Explored dataset structure, data types, and summary statistics
- Checked for missing values, duplicate rows, and duplicate Patient IDs
- Reviewed unique values across all categorical columns

### 2. Data Cleaning
- Standardized `Gender` labels (merged M/F/Other variants into consistent categories)
- Cleaned `City` and `Diagnosis` text — fixed casing, whitespace, and typo variants (e.g. "Mumbaii" → "Mumbai", "Chennaii" → "Chennai")
- Validated `Age`, flagging values outside a realistic range and filling with the column median
- Parsed `AdmissionDate` / `DischargeDate` and corrected impossible date logic (discharge date earlier than admission date)
- Cleaned `BillingAmount` — stripped currency symbols/commas, corrected negative values, capped extreme outliers at the 99th percentile
- Standardized `InsuranceProvider` labels, grouping missing/"N/A" style entries under **Self Pay**
- Handled missing values across `Name`, `DoctorName`, and `Department`
- Removed duplicate records
- Engineered a new `LengthOfStay` feature from the admission and discharge dates

### 3. Exploratory Data Analysis
- Department-wise patient volume, average length of stay, and average billing
- Monthly admission trend across the full date range
- Age distribution across six age bands
- Top revenue-generating cities and insurance provider mix
- Correlation check between Age, Length of Stay, and Billing Amount

### 4. Visualization & Dashboard
- Static charts (bar, line, boxplot, correlation heatmap, pie) built in the notebook with Matplotlib/Seaborn
- A live interactive dashboard (`index.html`) built from the same cleaned data, with a clickable department filter and hand-drawn SVG charts

## Key Insights
- Patient volume is nearly identical across all 12 clinical departments (~12,000–12,400 admissions each) — cost, not caseload, is what separates them
- **Oncology** and **Cardiology** carry the highest average billing per admission, despite similar patient volume and length of stay to other departments
- Monthly admission volume is stable year-round, with no strong seasonal spike
- About 20% of admissions had no listed insurer and were standardized to a single category during cleaning

## Tools Used
Python · Pandas · NumPy · Matplotlib · Seaborn · Jupyter Notebook · Vanilla JavaScript & SVG (dashboard)

## Repository Structure
```
├── Healthcare_Project__Python_Parv.ipynb   # main notebook
├── healthcare_dataset_raw.csv              # raw data
├── healthcare_clean.csv                    # cleaned data
├── index.html                              # live interactive dashboard
└── README.md
```

## How to Run
**Notebook:**
1. Clone this repository
2. Install dependencies:
   ```
   pip install pandas numpy matplotlib seaborn
   ```
3. Open `Healthcare_Project__Python_Parv.ipynb` in Jupyter and run all cells top to bottom

**Dashboard:**
- Open `index.html` directly in any browser, or enable **GitHub Pages** on this repo (Settings → Pages → Deploy from branch → `main` / root) to get a live public link

## Connect with Me
- GitHub: [github.com/parvjain921](https://github.com/parvjain921)
- LinkedIn: [linkedin.com/in/parv-jain-6b3038419](https://www.linkedin.com/in/parv-jain-6b3038419)
