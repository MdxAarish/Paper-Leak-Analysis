# Paper Leak Analysis

## Project Overview

This project analyzes recorded examination paper-leak incidents in India from 2004 to 2026 using Python and Pandas. The analysis follows a step-by-step data-analysis workflow covering data loading, extraction, validation, cleaning, aggregation, analysis, visualization, and interpretation.

**Team:** Team 08  
**Course:** Data Analysis Essentials (DAE)  
**Dataset:** India Paper Leaks (2004–2026)

---

## Problem Statement

Paper-leak incidents can disrupt examinations, delay results, and affect large numbers of candidates. The recorded incidents in the dataset occur across different areas, examination types, and conducting bodies, and several impact variables contain missing information.

The project uses a reproducible data-analysis process to study patterns in the recorded incidents and to compare their reported impact, legal response, actions taken, and other available attributes.

---

## Objectives

- Study recorded paper-leak trends in India from 2004–2026.
- Identify patterns across years, areas, examinations, and conducting bodies.
- Examine leak-status categories such as Confirmed, Alleged, Suspected, and Denied.
- Analyze reported aspirant impact where the information is available.
- Examine arrests, convictions, actions taken, linked deaths, and confidence separately.
- Clean and standardize the dataset before aggregation and visualization.
- Present findings using tables, statistical summaries, and charts.

---

## Scope and Significance

### Scope

The project is limited to the incidents represented in the supplied dataset. It covers records from 2004 through 2026 and focuses on incident details, examination information, geographic area, conducting bodies, reported impact, legal response, actions taken, source information, and confidence.

### Significance

The analysis provides a structured way to understand patterns in the recorded paper-leak incidents. It helps organize information that can otherwise be difficult to compare across different years, examinations, areas, and conducting bodies. The results are intended for data-analysis and educational purposes and should not be interpreted as a complete count of every paper-leak incident in India.

---

## Dataset

### Source

The project uses the **India Paper Leaks from 2004 to 2026** dataset from Kaggle.

Dataset/reference page:  
https://www.kaggle.com/code/devraai/indian-paper-leaks-analysis-and-prediction

### Dataset Description

The raw project dataset contains:

- **110 records (incidents)**
- **18 columns (fields)**
- Date range: **2004–2026**
- Leak-status categories: **89 Confirmed, 13 Alleged, 3 Suspected, 5 Denied**

Important attributes include:

- `incident_id` — unique incident identifier
- `date` — incident date
- `era` — time-period category
- `exam_name` — examination involved
- `conducting_body` — organization conducting the examination
- `body_type` — Central or State
- `area` — recorded geographic area
- `leak_status` — Confirmed, Alleged, Suspected, or Denied
- `action_taken` — recorded response/action
- `arrests` — reported arrests where available
- `convictions` — reported convictions where available
- `aspirants_affected` — reported aspirant impact where available
- `linked_deaths` — recorded linked deaths where available
- `source_name` and `source_url` — source information
- `confidence` — confidence/context indicator

### Data Availability

The source data does not contain every impact variable for every incident. In the current dataset:

- Reported aspirant impact is available for **44 of 110** incidents.
- Arrest information is available for **63 of 110** incidents.
- Conviction information is available for **10 of 110** incidents.
- Linked-death information is available for **4 of 110** incidents.

Missing values are kept as missing and are **not automatically treated as zero**.

---

## Project Workflow

The repository follows four practical stages:

1. **Data Loading & Reading**
2. **Data Extraction, Validation & Cleaning**
3. **Data Aggregation, Representation & Analysis**
4. **Data Visualization, Results & Interpretation**

The stages correspond to the larger data-analysis workflow used for the project.

---

## Repository Structure

```text
Paper-Leak-Analysis/
│
├── 01_Data_Loading_and_Reading/
│   ├── README.md
│   └── Project_Stage_1_Data_Loading_and_Reading.ipynb
│
├── 02_Data_Extraction_Validation_and_Cleaning/
│   ├── README.md
│   └── Project_Stage_2_Data_Extraction_Validation_Cleaning.ipynb
│
├── 03_Data_Aggregation_Representation_and_Analysis/
│   ├── README.md
│   └── Project_Stage_3_Data_Aggregation_Representation_Analysis.ipynb
│
├── 04_Data_Visualization_Results_and_Interpretation/
│   ├── README.md
│   └── Project_Stage_4_Data_Visualization_Results_Interpretation.ipynb
│
├── data/
│   ├── README.md
│   ├── paper_leaks.csv
│   └── paper_leaks_cleaned.csv
│
├── outputs/
│   └── figures/
│
├── README.md
├── requirements.txt
└── .gitignore
```

---

## Data Processing and Analysis

### Data Loading and Inspection

Stage 1 loads the dataset and performs basic inspection, including:

- first and last records
- dataset dimensions
- column names
- data types
- dataset information
- descriptive statistics
- categorical-value exploration
- basic filtering of records

### Missing Values and Duplicate Checks

Stage 2 checks for:

- missing values
- missing-value percentages
- duplicate records
- duplicate Incident IDs
- invalid Incident ID formats
- invalid dates
- dates outside the expected range
- blank text values
- leading/trailing whitespace

### Data Cleaning and Filtering

The cleaning stage applies only the transformations supported by the validation results. Examples include:

- standardizing spacing in the `action_taken` field
- converting `date` to a datetime type
- checking numerical columns
- preserving source missingness rather than replacing unreported values with zero
- performing final validation after cleaning

The raw dataset is preserved separately from the cleaned dataset.

### Aggregation and Analysis

Stage 3 uses Pandas operations such as:

- `groupby()`
- `agg()`
- `sum()`
- `count()`
- `sort_values()`
- filtering
- year extraction from dates
- comparisons across years, eras, areas, exams, and leak-status categories

The analysis also examines reported aspirant impact, arrests, convictions, and their relationships where the required data is available.

### Visualization

Stage 4 produces charts for:

- paper-leak cases by year
- top areas with recorded cases
- top examinations with recorded cases
- leak-status distribution
- cases by era
- arrests versus convictions

The charts are stored in `outputs/figures/`.

---

## Findings

The current dataset shows that:

- **2022** has the highest number of recorded incidents in the dataset, with **15 incidents**.
- `All India` is the most frequent recorded area label, with **16 incidents**, followed by Madhya Pradesh with **13**. Area labels have different geographic granularity, so these counts should be interpreted carefully.
- The dataset contains **89 Confirmed** incidents, while the remaining records are classified as Alleged, Suspected, or Denied.
- Reported aspirant-impact information is incomplete, so impact-based analysis is restricted to records where that information is available.
- Arrests and convictions are analyzed separately because they represent legal response/outcomes rather than direct incident impact.

The project should be read as an analysis of **recorded incidents in this dataset**, not as a complete national count of paper leaks.

---

## Impact-Based Analysis Note

For the project's impact-severity analysis, the methodology separates leak status from impact severity. A Confirmed incident is not automatically considered high impact.

The main severity analysis uses **Confirmed incidents with known reported aspirant impact**. The project applies a log transformation and dataset-derived percentile thresholds to classify relative impact into Low, Moderate, and High groups.

This classification is an **operational definition for this project**, not an official government severity standard.

---

## Limitations

- The dataset contains only recorded incidents represented in the source dataset.
- Several impact variables contain missing values.
- Missing values are not equivalent to zero.
- The reported meaning of `aspirants_affected` can vary between source records, so it is treated as reported aspirant impact rather than an exact count of every student affected.
- Geographic labels have different levels of detail, including states, cities, multiple locations, and `All India`.
- 2026 is a partial year and should not be compared directly with complete years without a caveat.
- Historical dates and incident descriptions may have source-specific limitations.
- Associations in the data should not be presented as proof of causation.

---

## How to Run the Project

### Requirements

Python 3 with the packages listed in `requirements.txt`.

Install the required packages using:

```bash
pip install -r requirements.txt
```

### Running in Google Colab

1. Open the required `.ipynb` notebook in Google Colab.
2. Run the cells from top to bottom.
3. When a notebook asks for a CSV file, upload the appropriate dataset from the `data/` folder.
4. Start with Stage 1 and continue through Stage 4.
5. Stage 2 produces the cleaned dataset used by the later analysis stages.

### Recommended Order

```text
Stage 1 → Stage 2 → Stage 3 → Stage 4
```

---

## Team Information

**Team Number:** 08

| Team Member | Roll Number | Contribution |
|---|---|---|
| N. Vedha Sri | 25B11CS659 | Data Loading, Reading & Filtering |
| Md Aarish | 25B11CS588 | Data Extraction, Validation & Cleaning |
| K. Harsha | 25B11CS389 | Data Aggregation,Representation & Analysis |
| V. Rishita Bhargavi | 25B11CS987 | Data Visualization, Results & Interpretation |

---

## Review Presentations

The Review-1 and Review-2 presentation files are included in the GitHub repository as required for project documentation.

---

## Tools and Technologies

- **Python 3**
- **Pandas** — data loading, filtering, cleaning, grouping, aggregation and transformation
- **NumPy** — numerical calculations and percentile-based analysis
- **Matplotlib** — data visualization
- **Google Colab / Jupyter Notebook** — notebook execution

---

## Conclusion

This project provides a structured analysis of recorded paper-leak incidents using a reproducible Python-based workflow. The analysis covers data quality checks, cleaning, aggregation, descriptive analysis, visualization, and interpretation while keeping the limitations of the source data visible throughout the process.
