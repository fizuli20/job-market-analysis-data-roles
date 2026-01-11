# Data Dictionary — Job Market Dataset

This document explains all columns in the `lukebarousse/data_jobs` dataset used throughout this analysis.

## Core Columns

| Column | Type | Description | Example |
|--------|------|-------------|---------|
| `job_id` | String | Unique identifier for the job posting | `123456` |
| `job_title` | String | Full job title as listed | `Senior Data Analyst` |
| `job_title_short` | String | Standardized short job title | `Data Analyst` |
| `job_location` | String | Location of the job posting | `New York, NY` |
| `job_country` | String | Country code of the job | `United States` |
| `job_posted_date` | DateTime | Date the job was posted | `2023-01-15` |
| `job_via` | String | Platform where job was posted | `LinkedIn`, `Indeed`, etc. |

## Salary & Compensation

| Column | Type | Description | Example |
|--------|------|-------------|---------|
| `salary_year_avg` | Float | Average annual salary in USD | `95000` |
| `salary_hour_avg` | Float | Average hourly rate in USD | `45.67` |
| `currency` | String | Currency of salary (if non-USD) | `USD`, `GBP`, `EUR` |
| `salary_currency_conv` | Float | Conversion rate to USD | `1.0` |

## Skills & Requirements

| Column | Type | Description | Example |
|--------|------|-------------|---------|
| `job_skills` | List | Top skills required for the role | `['Python', 'SQL', 'Tableau']` |
| `job_description` | String | Full job description text | `"We are looking for..."` |

## Company Information

| Column | Type | Description | Example |
|--------|------|-------------|---------|
| `company_name` | String | Company hiring for the role | `Tech Corp Inc.` |
| `company_size` | String | Size classification of company | `Large`, `Medium`, `Small` |

## Remote Work

| Column | Type | Description | Example |
|--------|------|-------------|---------|
| `job_work_from_home` | Boolean | Whether role supports remote work | `True`, `False` |

## Key Notes

- **Missing Values:** Some postings may not include salary information (`salary_year_avg = NaN`)
- **Skills Format:** `job_skills` is stored as a string representation of a Python list and requires parsing with `ast.literal_eval()`
- **Date Format:** All dates are in ISO 8601 format (YYYY-MM-DD)
- **Currency:** Most salaries are in USD; others are converted to USD equivalents
- **Job Titles:** Short titles are standardized; full titles may vary by company

## Common Job Title Categories

- **Data Analyst** — Business intelligence, reporting, data visualization
- **Data Engineer** — Pipeline development, ETL, infrastructure
- **Data Scientist** — Modeling, ML, statistical analysis
- **Senior roles** — 5+ years experience, leadership responsibilities
- **Machine Learning Engineer** — ML pipeline development, model deployment

## Data Quality Notes

- Dataset sourced from job boards aggregated via Hugging Face Hub
- Regular updates with fresh job postings
- Some entries may have incomplete information (e.g., salary, skills)
- Geographic data standardized to country level

---

*For more information, visit: [lukebarousse/data_jobs](https://huggingface.co/datasets/lukebarousse/data_jobs)*
