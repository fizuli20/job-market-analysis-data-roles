# Analysis Summary — Job Market Data

This document provides a detailed breakdown of all analyses performed across the notebook collection. **Quick links** to visualizations are provided in each section.

---

## Quick Navigation

| # | Analysis | Visualizations |
|---|----------|---|
| 1 | Data Cleaning | N/A |
| 2 | Salary & Skills | [Bar chart: Projected Salary](Analysis%20of%20salary%20and%20top%20skills.ipynb) \| [Skill Distribution Charts](Analysis%20of%20salary%20and%20top%20skills.ipynb) |
| 3 | Q1 2023 Trends | [Quarterly Analysis](analyzing%20first%20quarter%20of%202023.ipynb) |
| 4 | Monthly Trends | [Monthly Volume Charts](analyzing%20monthly%20job%20posting.ipynb) |
| 5 | Salary-Volume Correlation | [Scatter & Distribution Charts](analyzing%20salaries%20and%20job%20postings.ipynb) |
| 6 | USA Top Tech Jobs | [Ranking Bar Charts](Top%205%20tech%20jobs%20in%20USA.ipynb) |

---

## 1. Data Cleaning and Management

**File:** [`data cleaning and management.ipynb`](data%20cleaning%20and%20management.ipynb)

**Objectives:**
- Load data from Hugging Face datasets
- Identify and handle missing values
- Convert data types (e.g., dates, categories)
- Validate data consistency
- Prepare clean dataset for downstream analysis

**Key Outputs:**
- Cleaned dataframe ready for analysis
- Data quality report (null counts, duplicates)
- Feature engineering steps (e.g., date parsing)

**Skills Demonstrated:**
- Data validation
- Type casting
- Handling missing data
- Data integrity checks

---

## 2. Salary and Top Skills Analysis

**File:** [`Analysis of salary and top skills.ipynb`](Analysis%20of%20salary%20and%20top%20skills.ipynb)

**Objectives:**
- Analyze salary distributions by job title and geography
- Identify top skills demanded per role
- Compare compensation across roles
- Detect salary outliers and ranges

**📊 View Visualizations:**
- **Cell 4:** Projected salary comparison (bar chart comparing actual vs. inflation-adjusted salaries by role)
- **Cell 8:** Top 5 skills per job title (horizontal bar charts for Data Analyst, Engineer, Scientist)

**Key Outputs:**
- Median, min, max, and quartile salary statistics
- Top 10 skills by job title (Data Analyst, Engineer, Scientist)
- Salary distribution plots
- Geographic salary comparisons

**Key Insights:**
- Data Engineer roles command higher median salaries
- Specific technical skills correlate with higher compensation
- Geographic variations in salary expectations

**Skills Demonstrated:**
- Statistical analysis (median, quartiles, distributions)
- Groupby and aggregation operations
- Visualization of distributions (histograms, box plots)
- Comparative analysis

---

## 3. Q1 2023 Analysis

**File:** [`analyzing first quarter of 2023.ipynb`](analyzing%20first%20quarter%20of%202023.ipynb)

**Objectives:**
- Filter and analyze job postings from Q1 2023 (Jan–Mar)
- Identify hiring trends during this period
- Compare against other quarters
- Detect seasonal patterns

**📊 View Visualizations:**
- **Cells 3–5:** Quarterly filtering and trend visualizations (line charts, bar charts)
- **Cells 6–7:** Seasonal pattern detection and comparisons

**Key Outputs:**
- Monthly job posting volumes
- Role distribution in Q1
- Geographic hiring activity in Q1
- Trend comparisons

**Key Insights:**
- Q1 2023 hiring activity and trends
- Seasonal variations in job demand
- Regional hiring patterns

**Skills Demonstrated:**
- Date-time filtering and extraction
- Temporal aggregation
- Time-series trend detection
- Period comparison

---

## 4. Monthly Job Posting Analysis

**File:** [`analyzing monthly job posting.ipynb`](analyzing%20monthly%20job%20posting.ipynb)

**Objectives:**
- Track job posting volume trends month-over-month
- Identify peak hiring seasons
- Analyze role distribution by month
- Detect cyclical patterns

**📊 View Visualizations:**
- **Cells 4–5:** Monthly trend line charts (posting volume over time)
- **Cells 6–7:** Role-by-month heatmaps and stacked bar charts

**Key Outputs:**
- Monthly posting counts by role
- Line charts showing trends
- Seasonal peak identification
- Year-over-year growth rates

**Key Insights:**
- Peak hiring months for each role
- Seasonal hiring cycles
- Growth trends in job market

**Skills Demonstrated:**
- Time-series aggregation
- Trend visualization
- Seasonal decomposition
- Month-level grouping and analysis

---

## 5. Advanced Functions for Analysis

**File:** [`using advanced functions for analysis.ipynb`](using%20advanced%20functions%20for%20anaylysis.ipynb)

**Objectives:**
- Demonstrate advanced pandas operations
- Apply custom transformations using `apply()` and `lambda()`
---

## 4. Monthly Job Posting Trends

**File:** [`analyzing monthly job posting.ipynb`](analyzing%20monthly%20job%20posting.ipynb)

**Objectives:**
- Track job posting volume by month
- Identify seasonal hiring patterns
- Compare trends across roles
- Visualize temporal trends

**📊 View Visualizations:**
- Line charts showing monthly posting volume
- Seasonal pattern comparisons
- Trend lines for market dynamics

**Key Insights:**
- Seasonal hiring cycles in data job market
- Peak months for job postings
- Consistency or volatility of hiring

**Skills Demonstrated:**
- Time-series aggregation
- Trend visualization
- Temporal pattern detection
- Line chart creation

---

## 5. Salary and Job Posting Correlation Analysis

**File:** [`analyzing salaries and job postings.ipynb`](analyzing%20salaries%20and%20job%20postings.ipynb)

**Objectives:**
- Analyze relationship between salary and hiring volume
- Identify market dynamics
- Compare roles on multiple dimensions
- Detect compensation-demand patterns

**📊 View Visualizations:**
- Scatter plots and distribution charts
- Multi-variable comparative analysis
- Correlation visualization

**Key Insights:**
- How salary relates to job availability
- Market efficiency indicators
- Strategic career insights based on supply-demand

**Skills Demonstrated:**
- Multi-variable aggregation
- Correlation analysis
- Scatter plot visualization
- Business insights from data

---

## 6. Top 5 Tech Jobs in USA

**File:** [`Top 5 tech jobs in USA.ipynb`](Top%205%20tech%20jobs%20in%20USA.ipynb)

**Objectives:**
- Identify top data roles in the US market
- Rank roles by hiring volume
- Analyze regional market composition
- Compare USA to global trends

**📊 View Visualizations:**
- Bar charts ranking top roles
- Volume comparisons by role
- Professional ranking charts

**Key Insights:**
- Most in-demand data roles in USA
- Relative market size for each role
- Competition levels by role

**Skills Demonstrated:**
- Geographic filtering
- Ranking and sorting
- Aggregation by groups
- Professional visualization

---

## Summary of Competencies

| Competency | Notebooks | Level |
|------------|-----------|-------|
| Data Cleaning | Notebook 1 | Advanced |
| EDA & Statistics | Notebook 2 | Advanced |
| Time-Series Analysis | Notebooks 3, 4 | Advanced |
| Correlation Analysis | Notebook 5 | Advanced |
| Data Visualization | All notebooks | Advanced |
| Geographic Analysis | Notebook 6 | Advanced |
| Business Insights | All notebooks | Advanced |

---

## Tools & Technologies

- **Python 3.x** — Core language
- **Pandas** — Data manipulation, groupby, aggregations
- **Matplotlib** — Chart creation and styling
- **Seaborn** — Statistical visualization
- **Jupyter** — Interactive notebooks
- **Datasets** — Hugging Face API for data loading

---

## Data Source

- **Dataset:** `lukebarousse/data_jobs` (Hugging Face Hub)
- **Scope:** Real-world job postings for data roles globally
- **Roles Covered:** Data Analyst, Data Engineer, Data Scientist
- **Geography:** Multiple countries (USA, UK, Canada, Azerbaijan, etc.)

---

*Last updated: January 11, 2026*
