# 🌍 Global Education & Demographic Data Analysis

## Overview

This project explores global education and demographic data using **Python, Pandas, NumPy and Matplotlib**.

The analysis combines country-level demographic information with international education indicators to investigate patterns in enrolment, teacher availability, education expenditure, literacy and population characteristics.

The project focuses particularly on building a structured data-analysis workflow: starting with raw datasets, identifying inconsistencies, cleaning and reshaping the data, merging multiple data sources and transforming the resulting information into interpretable statistical and visual insights.

---

## 🎯 Project Objectives

The main objectives were to:

- clean and standardise raw education and demographic datasets
- identify inconsistencies between multiple data sources
- handle duplicates, missing values and incompatible data types
- reshape datasets for time-series analysis
- merge demographic and education data
- calculate new analytical metrics
- compare education indicators across countries and regions
- investigate relationships between demographic and education variables
- communicate findings through clear visualisations

---

## 🛠️ Technologies

**Programming & Analysis**

- Python
- Pandas
- NumPy
- Jupyter Notebook

**Visualisation**

- Matplotlib

**Key Techniques**

- Data cleaning
- Data filtering
- DataFrame manipulation
- Missing-value handling
- Data type conversion
- Dataset merging
- Wide-to-long data transformation
- GroupBy aggregation
- Pivot tables
- Feature engineering
- Correlation analysis
- Time-series analysis
- Data visualisation

---

## 📂 Data

The project uses two main datasets:

### Country Data

Contains country-level demographic information including variables such as:

- Country
- Region
- Population
- Land area

### Education Data

Contains international education indicators across multiple years, including:

- student enrolment
- teacher numbers
- government education expenditure
- adult literacy
- education level
- country and ISO codes

The two datasets were cleaned and aligned before being combined for cross-country analysis.

---

## 🔄 Analysis Workflow

```text
Raw Country Data + Raw Education Data
                 │
                 ▼
        Dataset Inspection
                 │
                 ▼
      Country Name Validation
                 │
                 ▼
          Data Cleaning
                 │
       ┌─────────┼─────────┐
       ▼         ▼         ▼
   Duplicates  Missing   Data Types
               Values
                 │
                 ▼
       Column Standardisation
                 │
                 ▼
        Data Transformation
         Wide → Long Format
                 │
                 ▼
          Dataset Merging
                 │
                 ▼
     Feature / Metric Creation
                 │
                 ▼
     Exploratory Data Analysis
                 │
                 ▼
   Cross-Country & Trend Analysis
                 │
                 ▼
          Visualisation
                 │
                 ▼
         Key Insights
```

---

## 🧹 Data Cleaning & Preparation

A substantial part of the project focused on transforming the raw datasets into analysis-ready DataFrames.

The cleaning process included:

- comparing country names across the two datasets
- retaining countries appearing in the required datasets
- renaming columns to clearer Python-friendly names
- standardising year columns
- detecting and removing duplicate rows
- converting missing-value indicators to `NaN`
- converting year-based values to numeric data types
- removing unnecessary whitespace from string columns
- validating DataFrame structures and data types

For example, original World Bank-style year columns were transformed into consistent names such as:

```python
year_2019
```

This made subsequent filtering, looping and time-series analysis considerably easier.

---

## 🔄 Data Transformation

For several analyses, the education dataset was transformed from **wide format to long format** using Pandas.

Techniques included:

```python
pd.melt()
groupby()
pivot_table()
merge()
```

Reshaping the data allowed education indicators to be analysed consistently across countries, education levels and years.

The project also demonstrates combining multiple datasets using common country identifiers and applying filtering logic to create analysis-specific subsets.

---

## 👩‍🏫 Teacher-to-Student Ratio Analysis

Teacher and student enrolment data were separated and subsequently merged using:

- Country
- ISO code
- Year
- Education level

This allowed teacher-to-student and student-to-teacher ratios to be calculated across different education levels.

The analysis included comparisons between **Germany and Switzerland** across:

- pre-primary education
- primary education
- secondary education

This demonstrates how raw education indicators can be transformed into more interpretable metrics for comparative analysis.

---

## 💰 Education Expenditure Analysis

Government expenditure on education was analysed over time for Switzerland.

The analysis dynamically identified year columns rather than hard-coding individual years and transformed them into values suitable for time-series visualisation.

The resulting trend showed relatively stable expenditure on secondary education over the available period, with moderate year-to-year fluctuations.

### Visualisation

![Education Expenditure Trend](images/education_expenditure_trend.png)

---

## 📚 Global Literacy Analysis

The project also investigated the **average adult literacy rate across countries over time**.

Literacy-related observations were filtered from the education dataset and annual averages were calculated across available countries.

The resulting time-series analysis was used to explore how average reported literacy levels changed across the available years.

---

## 🇩🇪 🇨🇭 🇦🇹 DACH Education Comparison

A comparative analysis was performed for:

- Germany
- Switzerland
- Austria

Enrolment trends were analysed across three education levels:

- Pre-primary
- Primary
- Secondary

The analysis used a multi-panel visualisation to compare enrolment patterns over time.

Germany recorded the highest absolute enrolment levels among the three countries in the analysed data, while Switzerland and Austria had substantially smaller totals.

The analysis also showed relatively stable pre-primary and primary enrolment patterns across the available period, while Germany displayed a decline in secondary enrolment in the analysed years.

### Visualisation

![DACH Enrolment Comparison](images/dach_enrolment_comparison.png)

---

## 🌐 Population Density Analysis

Country population and land-area information were used to calculate:

```text
Population Density = Population / Land Area
```

Countries were then classified into population-density groups and ranked within their respective regions.

Using Pandas `groupby()` operations, the analysis identified the five countries with the highest calculated population density within each region.

This demonstrates the use of:

- calculated features
- conditional classification
- sorting
- regional grouping
- Top-N analysis

---

## 📖 Literacy & Population Integration

One analysis combined literacy information from the education dataset with population information from the country dataset.

The analysis estimated a range for the number of illiterate adults using an assumed adult population share of **65%–80%**.

The calculation followed the general structure:

```text
Illiteracy Rate = 100 − Literacy Rate

Estimated Adult Population
= Total Population × Adult Population Assumption

Estimated Illiterate Adults
= Adult Population × Illiteracy Rate
```

This part of the project demonstrates how separate datasets can be integrated to derive new analytical metrics.

---

## 📈 Correlation Analysis

The project also investigated whether a country's **land area** was associated with its **primary-school enrolment**.

Country-area data was merged with primary enrolment information, observations with missing values were removed, and the relationship was evaluated using Pandas correlation functionality.

A scatter plot was then created to visualise the relationship between the two numerical variables.

---

## 🔎 Additional Analysis

The notebook contains several additional investigations, including:

- identifying countries appearing in one dataset but not another
- identifying the country with the largest number of secondary teachers
- measuring changes in primary-school enrolment between 2018 and 2019
- comparing countries with populations above 10 million
- identifying highly populated countries by region
- calculating average secondary enrolment by region
- analysing the ten smallest countries by land area
- comparing demographic and education indicators

---

## 💡 Key Takeaways

This project demonstrates the importance of **data preparation before analysis**.

The original datasets required substantial cleaning and restructuring before meaningful comparisons could be made. Country names needed to be aligned, missing values handled, year columns converted into numerical formats and datasets reshaped before indicators could be merged reliably.

It also demonstrates how Pandas operations such as:

```python
melt()
merge()
groupby()
pivot_table()
isin()
sort_values()
```

can be combined to answer different analytical questions using the same underlying datasets.

The project strengthened my understanding of building a reproducible workflow from **raw data → cleaned data → transformed data → analysis → visualisation → interpretation**.

---

## ⚠️ Limitations

The analysis is dependent on the completeness of the underlying datasets.

Several education indicators contain missing observations for particular countries or years, meaning that not every analysis covers an identical population or time period.

Absolute country comparisons should also be interpreted carefully. For example, enrolment totals are influenced by population size, meaning that larger countries would generally be expected to report larger absolute student populations.

Some derived analyses also rely on explicit assumptions, such as the estimated 65%–80% adult share used in the literacy analysis.

---

## 🚀 Future Improvements

Potential extensions include:

- incorporating more recent education data
- creating reusable functions to reduce repeated filtering operations
- automating data-quality checks
- analysing education indicators on a per-capita basis
- adding interactive visualisations
- developing a Power BI dashboard
- comparing education expenditure with educational outcomes
- performing clustering to identify countries with similar education profiles
- building predictive models for selected education indicators

---

## 📁 Repository Structure

```text
Global-Education-Data-Analysis/
│
├── README.md
│
├── global_education_analysis.ipynb
│
├── raw_data/
│   ├── country_data.csv
│   └── education_data.csv
│
├── images/
│   ├── education_expenditure_trend.png
│   ├── teacher_student_ratio.png
│   └── dach_enrolment_comparison.png
│
├── report/
│   └── COMP1888_Coursework_Report.pdf
│
└── requirements.txt
```

---

## ▶️ Running the Project

Clone the repository and install the required libraries:

```bash
pip install pandas numpy matplotlib jupyter
```

Then open:

```text
global_education_analysis.ipynb
```

in Jupyter Notebook, JupyterLab or another compatible notebook environment.

Make sure the raw datasets remain in the expected `raw_data/` directory so the notebook can access them correctly.

---

## 🎓 Academic Context

This project was originally completed as part of the **COMP1888 Programming for Data Science** module within the **MSc Data Science and Its Applications** programme at the University of Greenwich.

For this portfolio repository, the project is presented as an end-to-end Python data-analysis case study focusing on data cleaning, transformation, integration, exploratory analysis and visualisation.

---

## 👤 Author

**Julia Legner**

MSc Data Science and Its Applications  
University of Greenwich

**Portfolio Focus:** Data Analytics • Business Intelligence • Python • Data Science
