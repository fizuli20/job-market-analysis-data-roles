# Methodology — Data Analysis Approach

## Overview

This document outlines the analytical methodology and decision-making process used throughout the job market analysis project.

---

## 1. Data Source & Collection

### Source: Hugging Face Hub
- **Dataset:** `lukebarousse/data_jobs`
- **Format:** Parquet files via the `datasets` library
- **Coverage:** Global job postings for data roles (Data Analyst, Engineer, Scientist)
- **Update Frequency:** Regular refreshes with new job postings

### Data Sampling
- All available records are used for analysis (no sampling applied)
- Analysis focuses on rows with complete salary information when examining compensation trends

---

## 2. Data Cleaning & Preparation

### Type Conversion
```python
df['job_posted_date'] = pd.to_datetime(df['job_posted_date'])
```
- **Reason:** Enables time-series analysis and temporal filtering
- **Impact:** Converts string dates to proper datetime objects for sorting/filtering

### Missing Value Handling
- **Salary columns:** Filled with median values (statistical imputation)
  - **Justification:** Median is robust to outliers and preserves distribution shape
  - **Alternative considered:** Forward-fill (rejected due to temporal gaps)
- **Other columns:** Analyzed as-is; missing values reported in output

### Duplicate Removal
- **Exact duplicates:** Removed across all columns
- **Business duplicates:** Removed by (job_title, company_name) combination
  - **Reason:** Same job at same company likely reposted; deduplicate for cleaner analysis

---

## 3. Exploratory Data Analysis (EDA)

### Salary Analysis
1. **Descriptive Statistics**
   - Calculated median, quartiles, min, and max by role
   - Used groupby aggregation for multi-dimensional summaries

2. **Inflation Adjustment**
   - Applied 3% adjustment for standard roles, 5% for senior roles
   - **Rationale:** Reflects typical cost-of-living increases and seniority premiums

### Skills Analysis
1. **Data Transformation**
   - Parsed `job_skills` column from string representation to list
   - Used `explode()` to create one row per skill
   - Applied `groupby()` for skill frequency counts

2. **Top Skills Identification**
   - Ranked skills by frequency within each job role
   - Selected top 5 per role for visualization clarity
   - **Decision:** Limited to top 5 to avoid visual clutter

---

## 4. Visualization Standards

### Design Principles Applied
- **Professional color palette:** Consistent, contrasting colors across charts
- **Clear labels:** All axes labeled with units and descriptions
- **Readable fonts:** Arial/default fonts, 11-13pt sizes for clarity
- **Tight layouts:** Used `plt.tight_layout()` to prevent label cutoff
- **Figure sizing:** 10-12 inches width for readability

### Chart Types Selected
- **Bar charts:** For categorical comparisons (salary by role, skill frequency)
- **Line charts:** For temporal trends (monthly job postings)
- **Histograms:** For distribution analysis
- **Horizontal bars:** For skill rankings (improves readability)

---

## 5. Analytical Decisions & Assumptions

### Temporal Filtering
- **Q1 2023 analysis:** Jan 1 – Mar 31, 2023
- **Assumption:** Job postings reflect true hiring demand during this period

### Geographic Scope
- **Unit:** Country-level analysis (not city-level)
- **Reason:** Reduces complexity, enables broader comparisons
- **Trade-off:** Loses city-level nuance but improves data volume per group

### Salary Currency
- **Normalization:** All salaries converted to USD
- **Reason:** Enables fair comparison across countries
- **Conversion rates:** Used dataset-provided rates

### Skill Identification
- **Definition:** Skills explicitly listed in `job_skills` column
- **Limitation:** Does not infer implied skills from job descriptions
- **Trade-off:** More objective but may miss implicit requirements

---

## 6. Quality Assurance

### Data Validation Steps
1. ✓ Verified date parsing with sample outputs
2. ✓ Checked null counts before/after imputation
3. ✓ Confirmed duplicate removal reduced row count as expected
4. ✓ Validated skill parsing with manual spot checks
5. ✓ Visual inspection of charts for outliers and anomalies

### Reproducibility
- All analysis code is self-contained in Jupyter notebooks
- No hard-coded file paths; data loaded from public Hugging Face Hub
- Seeds set for any random operations (if applicable)

---

## 7. Limitations & Future Improvements

### Current Limitations
1. **Salary data gaps:** ~30-40% of postings lack salary information (creates selection bias)
2. **Temporal scope:** Analysis limited to available dataset; seasonality may not generalize to other years
3. **Skills mismatch:** Alternative job titles not standardized (e.g., "ML Engineer" vs "Data Scientist")
4. **Geographic bias:** Some countries over-represented in dataset

### Recommended Future Work
- [ ] Add predictive modeling for missing salary values
- [ ] Implement multi-year trend analysis for seasonality validation
- [ ] Create skill clustering to identify skill families (e.g., "BI Tools," "Languages")
- [ ] Add company size and industry filters for deeper segmentation
- [ ] Develop interactive dashboards (Plotly/Streamlit)

---

## 8. Tools & Libraries

| Tool | Purpose | Version |
|------|---------|---------|
| **Pandas** | Data manipulation and aggregation | 2.0+ |
| **Matplotlib** | Static visualizations | 3.7+ |
| **Seaborn** | Statistical visualization (optional) | 0.12+ |
| **Datasets** | Hugging Face Hub integration | 2.14+ |
| **Jupyter** | Interactive notebooks | 1.0+ |

---

## Conclusion

This methodology balances **analytical rigor** with **practical insights**, using industry-standard techniques for data cleaning, EDA, and visualization. All decisions are documented to enable reproducibility and support audit trails for professional portfolios.

For questions or suggestions on methodology, please refer to the main [README.md](README.md).
