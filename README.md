# Healthcare Data Cleaning & Exploratory Data Analysis (Python)

**Author:** Parv Jain
- GitHub: [parvjain921](https://github.com/parvjain921)
- LinkedIn: [Parv Jain](https://www.linkedin.com/in/parv-jain-6b3038419)

## Overview
This project involves cleaning a messy, real-world-style healthcare admissions dataset and performing exploratory data analysis (EDA) and visualization using Python. The goal was to take raw, inconsistent hospital records and turn them into an analysis-ready dataset, then extract meaningful operational and financial insights from it.

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
- Validated `Age`, flagging values outside a realistic range
- Parsed `AdmissionDate` / `DischargeDate` and corrected impossible date logic (discharge date earlier than admission date)
- Cleaned `BillingAmount` — stripped currency symbols/commas, corrected negative values, capped extreme outliers at the 99th percentile
- Standardized `InsuranceProvider` labels, grouping missing/"N/A" style entries under **Self Pay**
- Handled missing values across `Name`, `DoctorName`, and `Department`
- Removed duplicate records
- Engineered a new `LengthOfStay` feature from the admission and discharge dates

### 3. Exploratory Data Analysis
- Department-wise patient volume and average length of stay
- Billing trends by department, city, and insurance provider
- Top revenue-generating cities

### 4. Visualization
- Bar chart — patient admissions by department
- Line chart — monthly admission trend
- Boxplot — billing amount distribution by department
- Correlation heatmap — Age, Length of Stay, and Billing Amount
- Pie chart — insurance provider share

## Tools Used
Python · Pandas · NumPy · Matplotlib · Seaborn · Jupyter Notebook

## Repository Structure
```
├── Healthcare_Project__Python_Parv.ipynb   # main notebook
├── healthcare_dataset_raw.csv              # raw data
├── healthcare_clean.csv                    # cleaned data
└── README.md
```

## How to Run
1. Clone this repository
2. Install dependencies:
   ```
   pip install pandas numpy matplotlib seaborn
   ```
3. Open `Healthcare_Project__Python_Parv.ipynb` in Jupyter and run all cells top to bottom

## Connect with Me
- GitHub: [github.com/parvjain921](https://github.com/parvjain921)
- LinkedIn: [linkedin.com/in/parv-jain-6b3038419](https://www.linkedin.com/in/parv-jain-6b3038419)
