# Housing Discrimination and Algorithmic Bias
**DATA 6550 | Group 2 | Spring 2026**

---

## Overview

This project investigates the relationship between historical housing discrimination and modern mortgage lending outcomes in the Twin Cities metropolitan area. Using racial covenant data from the Mapping Prejudice Project combined with HMDA mortgage records, we analyze how past discrimination continues to shape lending decisions today through two distinct mechanisms:

- **Data Bias** — historical discrimination embedded in modern property values, incomes, and neighborhood characteristics
- **Algorithmic Bias** — lending algorithms perpetuating racial disparities through proxy variables, producing disparate outcomes without explicitly considering race

The analysis covers **Hennepin County** (primary, with covenant data) and extends to **Ramsey County** for cross-county comparison.

---

## Repository Structure

```
DATA6550-Housing-Bias/
│
├── README.md                        ← You are here
├── final_report.pdf                 ← Final submitted report
│
├── Code/
│   ├── Ali/                         ← Momina Ali
│   ├── Hallikeri/                   ← [Teammate]
│   ├── Yadlapalli/                  ← [Teammate]
│   └── [Lastname4]/                 ← [Teammate]
│
├── Data/
│   ├── hennepin_analysis.csv        ← Preprocessed Hennepin dataset (provided)
│   ├── county_27123.csv             ← Ramsey County HMDA data (2024)
│
├── Collaboration/
│   ├── WeekA.pdf                    ← Meeting summary Week A
│
└── Analysis/
    ├── .png figures                    
    └── results/                    
```

---

## Data Sources

| Dataset | Source | Details |
|---------|--------|---------|
| Hennepin covenant + HMDA | Provided by instructor | Covenant density, property values, lending data by census tract |
| Ramsey County HMDA | [CFPB HMDA Data Browser](https://ffiec.cfpb.gov/data-browser/data/2024?category=counties&items=27123) | 15,223 mortgage applications, 2024 |
---

## Analysis Notebook

**`Code/Ali/Group2_Module4.ipynb`**

| Section | Description |
|---------|-------------|
| EDA | Race distribution, loan actions, approval rates, covenant distribution |
| Data Bias | Property values and approval patterns by covenant status and group |
| Algorithmic Bias | Logistic regression model, proxy variable analysis, disparate impact (80% rule), denial reasons by race, interest rate disparities |
| Ramsey Extension | Full replication of analysis pipeline for Ramsey County |
| County Comparison | Side-by-side Hennepin vs. Ramsey approval rates, property values, disparate impact ratios, and interest rates |

---

## Key Findings

- Tracts with the highest covenant density show significantly lower property values and applicant incomes, demonstrating data bias embedded in modern lending inputs
- A logistic regression model using no race variable still produces racially disparate predictions — `tract_minority_population_percent` and `covenant_count` act as proxy variables for race
- Black or African American and American Indian or Alaska Native applicants face the largest approval-rate gaps in both counties
- Approved minority borrowers pay statistically significantly higher interest rates than White borrowers (Ramsey: t = −33.34, p < 0.0001)
- Disparities are consistent across both counties, indicating systemic regional bias rather than county-specific conditions

---

## How to Run

1. Clone the repository:
```bash
git clone https://github.com/MominaLAli/DATA6550-Housing-Bias.git
cd DATA6550-Housing-Bias
```

2. Install dependencies:
```bash
pip install pandas numpy matplotlib seaborn scikit-learn scipy
```

3. Place data files in `Data/` and open the notebook:
```bash
jupyter notebook Code/Ali/Group2_Module4.ipynb
```

---

## Team

| Name | Folder |
|------|--------|
| Momina Ali | `Code/Ali/` |
| [Teammate] | `Code/Hallikeri/` |
| [Teammate] | `Code/Yadlapalli/` |
| [Teammate] | `Code/[Lastname4]/` |

---

## Instructor Access

- **Instructor collaborator:** jfwallin
- **Google Doc (live report):** [add link]
- **D2L submission:** Group Dropbox — Module 4

---

*Course: DATA 6550 | Instructor: Dr. Wallin | Semester: Spring 2026*
